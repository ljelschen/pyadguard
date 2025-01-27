# Python: AdGuard Home API Client

PyAdguard is an API wrapper inspired by the repository Proxmoxer:  
https://github.com/proxmoxer/proxmoxer/tree/develop

## About

A simple alternative API to interact with AdGuard Home.  
Using the given AdGuardHome API description to get the needed URL paths:  
https://github.com/AdguardTeam/AdGuardHome/blob/master/openapi/openapi.yaml

## Installation


Normal installation:
```bash
pip install pyadguard
```

Local installation:
```bash
git clone https://github.com/ljelschen/pyadguard.git
cd pyadguard
pip install .
```

## Usage
Modify the given `sample.env` and rename the file to `.env`

```py
# %% imports
from pyadguard import AdguardAPI
from dotenv import dotenv_values

config = dotenv_values(".env")

# %% create an instance of AdguardAPI
adguard = AdguardAPI(
    host=config["ADGUARD_HOST"],
    username=config["ADGUARD_USERNAME"],
    password=config["ADGUARD_PASSWORD"],
    backend="https"
)
# %% read the stats of the AdGuard Home instance

# the url is /stats
stats = adguard.stats.get()
print(stats)
```

More examples are included in the examples folder.

## Changelog & Releases

Details of changes and releases will be documented here.

## Contributing

Guidelines for contributing will be provided here.

## Setting Up the Development Environment

Instructions for setting up the development environment will be provided here.

## Authors & Contributors

The original setup of this repository is by Lars Jelschen.

## License

MIT License  

Copyright (c) 2025 Lars Jelschen

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.