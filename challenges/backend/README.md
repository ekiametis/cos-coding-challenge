This a simple project that consists in consume the car-on-sale API just to authenticate a buyer and retrieve their running auctions to calculate some metrics based in the response. There's a Auction Monitor that see all required information.

If something get wrong the node process needs to terminate with exit code -1, and if it get success exit the process with code 0.

**Goal**: `The project was developed just to resolve the challenge:` [CarOnSale Challenge](https://github.com/car-on-sale/cos-coding-challenge/tree/master/challenges/backend)

**OpenAPI specification**: https://api-core-dev.caronsale.de/swagger/#/

# Summary

* [1. Pre-requirements](#1-pre-requirements)
* [2. HOW TO RUN?](#2-how-to-run)
* [3. HOW TO TEST?](#3-how-to-test)
* [4. HOW TO SEE THE COVERAGE?](#4-how-to-see-the-coverage)
* [5. Architecture](#5-architecture)
* [NOTES](#notes)

# 1. Pre-requirements

- NodeJS 12+ installed
- Execute following command: `npm install`

# 2. HOW TO RUN?

You can run the following commands:
```
npm run start
```

# 3. HOW TO TEST?

You can run the following commands:
```
npm test
```

# 4. HOW TO SEE THE COVERAGE?

You can run the following commands:
```
npm run coverage
```

# 5. Architecture

The project is splitted in a few folder, for example:

- 1. `src` - Is the main folder where the typescript code was written.
  - 1.1. `components` - It's a component folder where we can develop our abstractions to implement some pattern or system behaviour, for example: http client, logger, tracing, metrics. This folder is a strong candidate to be a npm module.
  - 1.2. `config` - All configurations we have to load on this project are located in this folder.
  - 1.3. `helpers` - Folder which includes many kinds of utility functions.
  - 1.4. `services` - It's a folder structured to write use cases bussiness services and the test specification. By this way we can notice and develop high cohesion code and split our system modules in a good format respecting SOLID principles. 

# NOTES

- As I mentioned before, this is a simple solution to resolve the challenge proposed by Car On Sale and I resolved to follow the structure pattern showed and implemented in the challenge repository. But I would put together the classes and interfaces in the same directories, because interfaces are following a pattern where we can start the name of it beggining with the letter 'I'.

- I used interfaces to declare dependencies in some classes following the Dependency Inversion pattern explained in the S.O.L.I.D. principles. Because it becomes more easy to change implementations when passing it as arguments to some classes.