# rocm_lib
Crate bringing support for rocm-smi liblary from C

# Instalation

## Manjaro
```
sudo pacman -S rocm-smi-lib rocm-smi
```

## Fedora / RHEL

Create file named `/etc/yum.repos.d/rocm.repo` and write it with:
```
[ROCm-5.5.3]
name=ROCm5.5.3
baseurl=https://repo.radeon.com/rocm/rhel9/5.5.3/main
enabled=1
priority=50
gpgcheck=1
gpgkey=https://repo.radeon.com/rocm/rocm.gpg.key
```
> For suse change file path to /etc/zypp/repos.d/rocm.repo `baseurl` to `https://repo.radeon.com/rocm/zyp/5.5.3/main` 
Then run 
On Fedora:
```
sudo dnf install rocm-smi rocm-smi-devel
```
On RHEL:
```
sudo yum install --nogpgcheck rocblas rocm-smi-lib
```
On Suse:
```
sudo zypper install rocblas rocm-smi-lib
```

## Ubuntu 

Run commands:
```
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/rocm.gpg] https://repo.radeon.com/rocm/apt/$ver focal main" \
    | sudo tee --append /etc/apt/sources.list.d/rocm.list

echo -e 'Package: *\nPin: release o=repo.radeon.com\nPin-Priority: 600' \
    | sudo tee /etc/apt/preferences.d/rocm-pin-600

sudo apt update

sudo apt install rocm-dkms rocm-dev rocm-smi-lib
```