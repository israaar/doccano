<div align="center">
  <img src="./docs/images/logo/doccano.png">
</div>

# doccano

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/98a0992c0a254d0ba23fd75631fe2907)](https://app.codacy.com/app/Hironsan/doccano?utm_source=github.com&utm_medium=referral&utm_content=doccano/doccano&utm_campaign=Badge_Grade_Dashboard)
[![Build Status](https://travis-ci.com/doccano/doccano.svg?branch=master)](https://travis-ci.com/doccano/doccano)

doccano is an open source text annotation tool for humans. It provides annotation features for text classification, sequence labeling and sequence to sequence tasks. So, you can create labeled data for sentiment analysis, named entity recognition, text summarization and so on. Just create a project, upload data and start annotating. You can build a dataset in hours.

## Demo

You can try the [annotation demo](http://doccano.herokuapp.com).

![Demo image](./docs/images/demo/demo.gif)

## Features

- Collaborative annotation
- Multi-language support
- Mobile support
- Emoji :smile: support
- Dark theme
- RESTful API

## Usage

Two options to run doccano:

- Production
- Development

In any case, you need Docker and Docker Compose. Anyway, you need to clone the repository:

```bash
$ git clone https://github.com/doccano/doccano.git
$ cd doccano
```

_Note for Windows developers: Be sure to configure git to correctly handle line endings or you may encounter `status code 127` errors while running the services in future steps. Running with the git config options below will ensure your git directory correctly handles line endings._

```bash
git clone https://github.com/doccano/doccano.git --config core.autocrlf=input
```

### Production

```bash
$ docker-compose -f docker-compose.prod.yml up
```

Go to <http://0.0.0.0/>.

Note the superuser account credentials located in the `docker-compose.prod.yml` file:

```yml
ADMIN_USERNAME: "admin"
ADMIN_PASSWORD: "password"
```

> Note: If you want to add annotators, see [Frequently Asked Questions](./docs/faq.md)

<!--

### Docker

As a one-time setup, create a Docker container for Doccano:

```bash
docker pull doccano/doccano
docker container create --name doccano \
  -e "ADMIN_USERNAME=admin" \
  -e "ADMIN_EMAIL=admin@example.com" \
  -e "ADMIN_PASSWORD=password" \
  -p 8000:8000 doccano/doccano
```

Next, start Doccano by running the container:

```bash
docker container start doccano
```

To stop the container, run `docker container stop doccano -t 5`.
All data created in the container will persist across restarts.

Go to <http://127.0.0.1:8000/>.

-->

### Development

```bash
$ docker-compose -f docker-compose.dev.yml up
```

Go to <http://127.0.0.1:3000/>.

## One-click Deployment

| Service | Button |
|---------|---|
| AWS[^1]   | [![AWS CloudFormation Launch Stack SVG Button](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home?#/stacks/create/review?stackName=doccano&templateURL=https://s3-external-1.amazonaws.com/cf-templates-10vry9l3mp71r-us-east-1/2019290i9t-AppSGl1poo4j8qpq)  |
| Azure | [![Deploy to Azure](https://azuredeploy.net/deploybutton.svg)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdoccano%2Fdoccano%2Fmaster%2Fazuredeploy.json)  |
| GCP[^2] | [![GCP Cloud Run PNG Button](https://storage.googleapis.com/gweb-cloudblog-publish/images/run_on_google_cloud.max-300x300.png)](https://console.cloud.google.com/cloudshell/editor?shellonly=true&cloudshell_image=gcr.io/cloudrun/doccano&cloudshell_git_repo=https://github.com/doccano/doccano.git)  |
| Heroku  | [![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)  |

> [^1]: (1) EC2 KeyPair cannot be created automatically, so make sure you have an existing EC2 KeyPair in one region. Or [create one yourself](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#having-ec2-create-your-key-pair). (2) If you want to access doccano via HTTPS in AWS, here is an [instruction](https://github.com/doccano/doccano/wiki/HTTPS-setting-for-doccano-in-AWS).
> [^2]: Although this is a very cheap option, it is only suitable for very small teams (up to 80 concurrent requests). Read more on [Cloud Run docs](https://cloud.google.com/run/docs/concepts).

## Contribution

As with any software, doccano is under continuous development. If you have requests for features, please file an issue describing your request. Also, if you want to see work towards a specific feature, feel free to contribute by working towards it. The standard procedure is to fork the repository, add a feature, fix a bug, then file a pull request that your changes are to be merged into the main repository and included in the next release.

Here are some tips might be helpful. [How to Contribute to Doccano Project](https://github.com/doccano/doccano/wiki/How-to-Contribute-to-Doccano-Project)

## Citation

```tex
@misc{doccano,
  title={{doccano}: Text Annotation Tool for Human},
  url={https://github.com/doccano/doccano},
  note={Software available from https://github.com/doccano/doccano},
  author={
    Hiroki Nakayama and
    Takahiro Kubo and
    Junya Kamura and
    Yasufumi Taniguchi and
    Xu Liang},
  year={2018},
}
```

## Contact

For help and feedback, please feel free to contact [the author](https://github.com/Hironsan).
