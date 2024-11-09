## PyZn - Python Zone for analytics 

<p>
  <a aria-label="KhulnaSoft logo" href="https://khulnasoft.com/"><img src="https://img.shields.io/badge/MADE%20BY%20KhulnaSoft-000000.svg?style=for-the-badge&logo=KhulnaSoft&labelColor=000"></a>
  <a aria-label="License" href="https://github.com/khulnasoft/pyzn/blob/main/LICENSE"><img alt="" src="https://img.shields.io/npm/l/turbo.svg?style=for-the-badge&labelColor=000000&color="></a>
</p>

[pyzn.kulnasoft.com](https://pyzn.kulnasoft.com) is a site which aims to show statistics about Python packages.

## ⚒️ Start contributing
I wanted to make the setup of the environment as easy as possible. To start the environment you need the 
following prerequisites:

### Prerequisites
  * bash (+4.3)
  * docker (+17.05)
  * docker-compose (+1.16.1)
  * docker-py (+2.2.1)
  * ansible (+2.3)
  
### Start environment
You only (_fingers crossed_) need to execute the following to start the environment:

```commandline
make start-containers
```

## Architecture and patterns
Principally I used some DDD concepts (like value objects, entities, and so on) and also CQS whose objective is to
separate commands from queries.

The structure of the code is the following:
  * `pyzn/application`: here is where all the commands and the queries are located.
  * `pyzn/domain`: domain objects like entities, exceptions, and value objects.
  * `pyzn/infrastructure`: infrastructure components like the implementation of the repository
    class like DB or BigQuery, the Flask web application, the container, and so on.
    * `pyzn/infrastructure/cli`: the command line programs.
    * `pyzn/infrastructure/container`: config files and the dependency injection manager.
    * `pyzn/infrastructure/api`: the api endpoints controller.


## 💖 Sponsors

We can keep alive the website thanks to you and also thanks to the following sponsors.

<!-- sponsors -->
<!-- sponsors -->

## FAQ
**Where the downloads come from?**

The data is retrieved from the official BigQuery repository: https://packaging.python.org/guides/analyzing-pypi-package-downloads/

**When the data is updated?**

There is a cron that runs every day at 5 pm UTC that retrieves all the new downloads from the previous day.

## 🚩 License
The code is available under the [MIT license](LICENSE.md).
