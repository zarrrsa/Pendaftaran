# Pendaftaran
Form pendaftaran santri baru
# tamplate pendaftaran santri
import datetime
import os
import string
import random
template_santri = {
    'nama':'nama',
    'alamat':'alamat',
    'lahir':datetime.datetime(1111,1,11)
}
data_santri = {}
while True:       
    os.system('cls')    
    print(f"{'SELAMAT DATANG':^20}")
    print(f"{'DATA SANTRI':^20}")
    print('-'*20)    

    santri = dict.fromkeys(template_santri.keys())
    santri['nama'] = input('Masukan Nama Santri: ')
    santri['alamat'] = input('Masukan Alamat Santri: ')
    TAHUN_LAHIR = int(input('Masukan Tahun Lahir (yyyy) : '))
    BULAN_LAHIR = int(input('Masukan Bulan Lahir (1-12) : '))
    TANGGAL_LAHIR = int(input('Masukan Tanggal Lahir (1-31) : '))
    santri['lahir'] = datetime.datetime(TAHUN_LAHIR,BULAN_LAHIR,TANGGAL_LAHIR)    

    KEY = ''.join((random.choice(string.ascii_uppercase) for i in range(6)))
    data_santri.update({KEY:santri})
    print(f"{'KEY':<7} {'NAMA':<6} {'ALAMAT':<42} {'LAHIR':<7} ")
    print("="*59)    

    for santri in data_santri:
        KEY = santri

        NAMA = data_santri [KEY] ['nama']
        ALAMAT = data_santri [KEY] ['alamat']
        LAHIR = data_santri [KEY] ['lahir'].strftime("%x")
        print(f"{KEY:<7} {NAMA:<6} {ALAMAT:<40} {LAHIR:^6}")
    is_done = input("Apakah Mau Tmabah (n/y) ? : ")
    if is_done == "n":
        break
