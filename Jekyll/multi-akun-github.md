# Multi Akun Gihub

## Step 1 - Create a New SSH Key.

Kita harus generate unik SSH Key untuk Github akun ke 2:

    ssh-keygen -t rsa -C "your-email-address"

Maka akan di generate SSH Key baru, hati-hati jangan tindih yang pertama gunakan nama lain contoh: /Users/dyo-medio/.ssh/id_rsa_namalain.

Kemudian cek pada folder .ssh anda maka akan ada  id_rsa.pub_namalain.

## Step 2 - Tambahkan New SSH Key ke github.com baru anda.

Tampilkan SSH Key yang baru di Terminal:

    cd .ssh
    cat id_rsa_namalain.pub

    // copy dan paste ke github baru anda

Kemudian kita harus tambahkan dengan perintah sbb:

    ssh-add ~/.ssh/id_rsa_namalain

Enter maka muncul: Identity added: /Users/dyo-medio/.ssh/id_rsa_xxx (/Users/dyo-medio/.ssh/id_rsa_xxx) 


## Step 3 - Membuat Config File.

    touch ~/.ssh/config

    // kemudian buka dengan:
    nano config dan isi dengan:

    #Default GitHub
    Host github.com
      HostName github.com
      User git
      IdentityFile ~/.ssh/id_rsa

    Host github-NAMALAIN
      HostName github.com
      User git
      IdentityFile ~/.ssh/id_rsa_namalain

## Step 4 - Coba dengan git.

Kembali ke folder project, kemudian lakukan update, lanjut dengan:

    git status
    git add .
    git commit 

Dan copy paste ini, jangan lupa di update dulu:

    git remote add origin git@github.com:kitabsakti-fullstackjs/kitabsakti-fullstackjs.github.io.git

Update menjadi seperti dibawah ini dimana HOST nya menyesuaikan dengan config yang sudah kita buat sebelumnya:

    git remote add kitabsakti git@github-KITABSAKTI:kitabsakti-fullstackjs/kitabsakti-fullstackjs.github.io.git

Kemudian push

    git push kitabsakti master

Kemudian cek ke github repo baru anda, jika tidak ada error maka web anda berhasil "kitabsakti-fullstackjs.github.io".

Pastikan anda masih bisa push ke github origin anda :)