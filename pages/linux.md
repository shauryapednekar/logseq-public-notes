subject:: [[subject/technologies]]

- [[Package Management]]
	- It uses APT (advanced package tool) to manage packages.
	- It maintains a bunch of `.list` files that point to repositories where it should look for packages.
		- The main repositories are in `/etc/apt/sources.list`, and custom repositories are specified in `/etc/apt/sources.list.d/`.
	- To verify that a package is the same as the one distributed by the developer (i.e. it hasn't been changed by any middleman), APT uses public key encryption with GPG to verify signatures. The basic principle here is that if a private key is used to sign a file, then anyone who has the corresponding public key can check that the file was signed by the private key. The signature cannot be forged without access to the private key. See