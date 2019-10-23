# Packer - CentOS 8.0 Vagrant Box With GNOME Desktop

**Current CentOS Version Used**: 8.0 (1905)

**Pre-built Vagrant Box**:

  - [`vagrant init nitindas/centos-8.0`](https://app.vagrantup.com/nitindas/boxes/centos-8.0)

This example build configuration installs and configures CentOS 8.0 x86_64.

## Requirements

The following software must be installed/present on your local machine before you can use Packer to build the Vagrant box file:

  - [Packer 1.2.5](http://www.packer.io/)
  - [Vagrant 2.2.6](http://vagrantup.com/)
  - [VirtualBox 6.0.14](https://www.virtualbox.org/) (if you want to build the VirtualBox box)
  - Vagrant cloud account username as password

## Usage

Make sure all the required software (listed above) is installed, then cd to the directory containing this README.md file, and run:

    $ centos8.0-packer-build.sh <VagrantCloud User/login> <VagrantCloud Password>

After a few minutes, Packer should tell you the box was generated successfully, and the box was uploaded to Vagrant Cloud.

> **Note**: This configuration includes a post-processor that pushes the built box to Vagrant Cloud (which requires a `VAGRANT_CLOUD_TOKEN` environment variable to be set); remove the `vagrant-cloud` post-processor from the Packer template to build the box locally and not push it to Vagrant Cloud. You don't need to specify a `version` variable either, if not using the `vagrant-cloud` post-processor.

## Testing built boxes

There's an included Vagrantfile that allows quick testing of the built Vagrant boxes. From VagrantFile-Example/ directory, run one the following command after building the box:

    $ cd VagrantFile-Example/
    $ vagrant up

## License

MIT license.