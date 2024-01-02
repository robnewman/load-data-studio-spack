# load-data-studio-spack
Test repo for loading a Data Studio directly from a Github repo using the [Spack package manager](https://spack.readthedocs.io/)

# Install Spack

1. Use [Homebrew](https://brew.sh/) to install [spack](https://formulae.brew.sh/formula/spack): `$ brew install spack`
2. Initialize: `$ . /opt/homebrew/Cellar/spack/0.21.0/share/spack/setup-env.sh`

# Steps to generate a Spack environment file

1. Create a Spack environment: `$ spack env activate myspackenv`
2. Add specific packages: 

  ```
  $ spack -e myspackenv add python py-jupyter py-jupyterlab py-jupyterlab-server
  ```

3. Install the packages: `$ spack -e myspackenv install`
4. The environment configuration file is stored at:

   ```
   /opt/homebrew/Cellar/spack/SPACK_VERSION/var/spack/environments/ENVIRONMENT_NAME/spack.yaml
   ```
   
5. Review the environment file in your editor of choice (Vim): `spack -e myenv config edit`
6. Copy to the Git repository:

  ```
  $ cp /opt/homebrew/Cellar/spack/SPACK_VERSION/var/spack/environments/ENVIRONMENT_NAME/spack.yaml /path/to/repository/spack.yaml
  ```

7. Add to the repo: `git add spack.yaml`
