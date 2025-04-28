# Wordpress Vulnerability Scanner
The aim of this project is to build a fairly easy to use open-source application that can help detect vulnerabilities on specifically wordpress websites, to help users, especially newer ones, effectively secure their websites.

Motivation:
So I would like my app to have the potential to be an open source wordpress website vulnerability scanner.

This product doesn't require a NIST API Key to work, but you get 10x faster download speeds with one, so I recommend obtaining one.

"This product uses the NVD API but is not endorsed or certified by the NVD."

## How to Run

Note: I refer to \[cd] below, I mean [In your terminal, change your working directory via the (cd) command]

1. To run this scanner, you'll first need to install docker.
2. Then do a git clone of this repo, and in your terminal, cd to the root of this repository.
3. In the root of this directory, run in your terminal:
    `docker compose up`
4. You should see the main script help function.
5. To change the arguments to the script, go to the docker-compose.yml, and change the `command: ["--help"]`. Then run
    `docker compose up`

```bash
usage: wp-cve-scanner.py [-h]
                           (--fetch-assets | --analyze | --generate-report | --do-all)
                           [--php {8.4,8.3,8.2,8.1,8.0,7.4,7.3,7.2,7.1,7.0}]
                           [--location {docker,local}] [--container CONTAINER]
                           [--path PATH] [--api-key API_KEY]
                           [--wp-assets WP_ASSETS]
                           [--analyzed-assets ANALYZED_ASSETS] [--output OUTPUT]
                           [--host]

WordPress Vulnerability Scanner

options:
    -h, --help            show this help message and exit
    --fetch-assets        Fetch WordPress assets.
    --analyze             Analyze WordPress assets for vulnerabilities.
    --generate-report     Generate a HTML report.
    --do-all              Fetch Assets, Analyze them and Generate a HTML report.
    --php {8.4,8.3,8.2,8.1,8.0,7.4,7.3,7.2,7.1,7.0}
                          PHP version used by WordPress. (default: 8.4).
                          Choices: [8.4, 8.3, 8.2, 8.1, 8.0, 7.4, 7.3, 7.2, 7.1,
                          7.0]
    --location {docker,local}
                          Location of the WordPress installation.
    --container CONTAINER
                          Name of the WordPress Docker container.
    --path PATH           Path to the WordPress installation.
    --api-key API_KEY     NIST API key for querying CVEs.
    --wp-assets WP_ASSETS
                          Input file for WordPress assets.
    --analyzed-assets ANALYZED_ASSETS
                          Input file for analyzed assets.
    --output OUTPUT       Output file for the HTML report.
    --host                Host the report on a Flask web page.
```

## Example Usage

To run this program, in your terminal cd to the root of this directory and run:
```bash
docker compose up
```

1. View the help

```
    entrypoint: ["python3", "wp-cve-scanner.py"]
    command: ["--help"] # Default command, can be overridden
```

2. Run all the functions with an API key

```
    entrypoint: ["python3", "wp-cve-scanner.py"]
    command: ["--do-all", "--location", "docker", "--container", "wordpress-install", "--php", "7.1", "--api-key", "YOUR-API-KEY-HERE", "--host"]
```

## License
This Wordpress-Vulnerability-Scanner is not currently available for general public use yet. This project is my year 3 dissertation project on my Computer Science with Cyber Security Course at the University of York.

```
Copyright (c) 2025 - https://github.com/hs1955/
Copyright (c) 2025 - University of York
```

This project makes use of NIST API. Specific Common Platform Enumerations (CPEs) and Common Vulnerabilities and Exposures (CVEs) mentioning Wordpress are obtained and downloaded from the NIST database.
