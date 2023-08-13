# stargazevanity

<!--- Don't edit the version line below manually. Let bump2version do it for you. -->
> Version 1.0.0

> CLI tool for generating [Stargaze](https://stargaze.zone/) vanity addresses


<details>
  <summary>Features:</summary>
  
* Generate Umee bech32 vanity addresses
* Use all CPU cores
* Specify a substring that the addresses must
    * start with
    * end with
    * contain
* Set required minimum amount of letters (a-z) or digits (0-9) in the addresses
* Binaries built for Linux, macOS and Windows
  
</details>


<details>
  <summary>Installing:</summary>
  
Download the latest binary release from the [_Releases_](https://github.com/g0odlike/cosmosvanity/releases) page. 

```sh
$ go version
go version go1.17 linux/amd64
$ git clone https://github.com/Northa/cosmosvanity.git && cd cosmosvanity
$ go build -o stargazevanity ./main.go

```
  
</details>

## Usage examples
Find an address that starts with "drew" (e.g. [stars1drewfmzk3a90m2ldkhxq0q7haaewkvfges05h0](https://www.mintscan.io/stargaze/accounts/stars1drewfmzk3a90m2ldkhxq0q7haaewkvfges05h0))
```sh
./stargazevanity --startswith drew
:::: Matching wallet 1/1 found ::::
Address:        stars1drewfmzk3a90m2ldkhxq0q7haaewkvfges05h0
Public key:     03e6334056ded1918964985d3501f2353a873a1d6c248849fa3c521f7b38a65c96
Private key:    9482108ab9d71fe7cf8c44c52ce2ea869337cb7a362a4d1cc51346b504054ce1
```

Find an address that starts with "nguru" (e.g. stars1ngurugw0m8ultdyr5zqr64puddxd8k5pm6pd80)
```sh
./stargazevanity --startswith nguru
:::: Matching wallet 1/1 found ::::
Address:        stars1ngurugw0m8ultdyr5zqr64puddxd8k5pm6pd80
Public key:     03104814aa00a270f20da6ba5d8ae8172b6d4d5954779c180487997a9558041f8c
Private key:    a79a2db65a5b92bff47bd11253fe880cf0995919bd5e1ab5ce701a909c6af1b1
```

Find an address that ends with "8888" (e.g. stars134dck5uddzjure8pyprmmqat96k3jlypn28888)
```bash
./stargazevanity --endswith 8888
```

Find an address containing the substring "gener" (e.g. stars1z39wgener7azgh22s5a3pyswtnjkx2w0hvn3rv)
```bash
./stargazevanity --contains gener
```

Find an address consisting of letters only (e.g. stars1rfqkejeaxlxwtjxucnrathlzgnvgcgldzmuxxe)
```bash
./stargazevanity --letters 38
```

Find an address with at least 26 digits (e.g. stars1r573c4086585u084926726x535y3k2ktxpr88l)
```bash
./stargazevanity --digits 26
```

Generate 5 addresses (the default is 1)
```bash
./stargazevanity -n 5
```

Restrict to using only 1 CPU thread. This value defaults to the number of CPUs available.
```bash
./stargazevanity --cpus 1
```

Combine flags introduced above
```bash
./stargazevanity --contains 8888 --startswith a --endswith c
```
