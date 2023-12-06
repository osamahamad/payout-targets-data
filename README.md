# Payout Targets Data Repository

## Overview
Inspired by [bounty-targets-data](https://github.com/arkadiyt/bounty-targets-data) this repository provides the latest in-scope targets from various public bug bounty platforms (BBPs) that offer rewards. Updated every 30 minutes, it includes a data folder and key output files such as assets.out, wildcards.out, new_added_assets.out, and new_added_wildcards.out. These files are a valuable resource for security researchers, offering up-to-date information.

> **Note**
> This repository is 100% automated so there can be false positives/negatives, but in general is pretty accurate. an example is the fact that if a public program was suspended and got unsuspended from a platform, it will be treated as a new program therefore its assets will be considered as a new scope and be included ( Similar to a company launching a brand new BB program on one of the monitored platforms) .  

## Repository Contents
- **Data Folder**: Contains continuously updated targets from platforms like Bugcrowd, HackerOne, Hackenproof, Intigriti, Federacy, and YesWeHack. This folder includes only those targets offering rewards.
- **assets.out**: A comprehensive list of unique assets across all monitored platforms, encompassing a wide range of in-scope items like mobile apps, source code, service names, child organization names, web hosts, and domain wildcards.
- **wildcards.out**: A list of in-scope wildcard domains extracted from the bounty data.
- **new_added_assets.out**: A file capturing newly identified assets since the last update. That means you can easily monitor all these platforms' new added in-scope assets or assets for new programs that just got launched and send notifications to your Telegram, Slack ..etc using a simple cronjob like this ``` */30 * * * * curl [raw.github.../new_added_assets.out](https://raw.githubusercontent.com/osamahamad/payout-targets-data/main/new_added_assets.out) | notify -provider-config telegram.yaml``` or you can enter this telegram channel https://t.me/publicbbprogramsmonitor
- **new_added_wildcards.out**: Shows newly identified wildcard domains since the last update. Running the above cron job for new_added_assets.out generally covers this, making a separate job for new_added_wildcards.out optional, or you can use it in a different way such as piping the results to your recon tools and keep your data about public programs up to date.


## Data Update Process
The data in this repository is automatically updated every 30 minutes by an external script, which:
- Fetches the latest data from public programs that offer rewards.
- Filters and processes this data to identify new and unique targets based on the previous run.
- Updates the repository with the latest findings.

## Usage
Researchers and security professionals can utilize this data for:
- Conducting security research and vulnerability assessments.
- Monitoring new targets in various bug bounty programs.
- Enhancing security tools with current target data especially when you don't to waste your bandwidth on VDPS with large scopes.

## Contributing
Contributions are welcome in the form of data analysis, additional data processing scripts, or suggestions for improvement. 

## License
This project is under the [MIT License](LICENSE).

## Acknowledgements
- Data sourced and processed based on information from [bounty-targets-data](https://github.com/arkadiyt/bounty-targets-data).
