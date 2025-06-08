## Tutorial Mining

- Install termux
  - Download di [Google Play](https://play.google.com/store/apps/details?id=com.termux&hl=en&gl=US)
- Adjust Termux
  - Perbaiki repositori yang rusak 
    ```bash 
    termux-change-repo
    ```
  - Install package yang dibutuhkan 
    ```bash 
    pkg install wget cmake
    ```
- Download Miner
  - ```bash
    wget https://github.com/dikripto/xmrig/archive/refs/heads/master.zip
    ```
  - Unzip file zip
    ```bash
    unzip master.zip
    ```
- Build Miner
  - Masuk ke folder miner
    ```bash 
    cd xmrig-master
    ```
  - Buat folder bernama `build` untuk menampung hasil build nanti 
    ```bash 
    mkdir build
    ```
  - Masuk ke folder `build`
   ```bash
   cd build
   ```
  - Proses konfigurasi build
    ```bash
    cmake .. -DWITH_HWLOC=OFF
    ```
  - Mulai proses build
    ```bash 
    make
    ```
- Konfigurasi Miner
  - Download config.json 
    ```bash
    wget https://gist.github.com/dytra/5b17acdd38fcabba83e6411f38cce5ad/raw/9214159292a479ec5c27ac7ea28d0da00ca99d4f/config.json 
    ```
  - Tampilkan full keyboard di termux. 
    ```bash 
    mkdir $HOME/.termux/ ;echo "extra-keys = [['ESC','/','-','HOME','UP','END'],['TAB','CTRL','ALT','LEFT','DOWN','RIGHT']]" >> $HOME/.termux/termux.properties && termux-reload-settings && sleep 1 && logout
    ```
  - Edit wallet address di config.json 
    ```bash 
    nano config.json
    ```
  - Edit line ke 94 sesuai keinginan
    `"user": "DOGE:D5wNKhb3fgnyk6NPEFtrgYta5YaSMg38pP.MBP#h1zg-9j2n",`
    > Keterangan `{NAMA KOIN}:{WALLET ADDRESS}.{NAMA WORKER}#{KODE REFERAL}`
  - Simpan File, (Tekan CTRL+X, lalu tekan Y,lalu tekan Enter)
- Jalankan miner
  - eksekusi miner 🤑 
    ```bash
    ./xmrig
    ```

### Cek Jumlah Koin yang Telah dimining

`https://www.unmineable.com/coins/{KOIN}/address/{WALLET_ADDRESS}`

contoh: `https://www.unmineable.com/coins/DOGE/address/abc123`
