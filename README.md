# Faculty System RESTful API Documentation

## ----------------------- {BASE_URL}/ -------------------------

### Check the RESTful API connectivity (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/>
  - Headers  
    Content-Type: application/json
- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
        "status": "success",
        "data": {
            "message": "Hello, Development!"
        },
        "message": null
    }
    ```
  
## ------------------- {BASE_URL}/api/auth -----------------------

### Authenticate the student (1)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/auth?username=18532968>
  - Headers  
    Content-Type: application/json
- Response
  - Headers  
    Auth-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuaW0iOiIxODUzMjk2OCIsImlhdCI6MTYxMDE3MzAwOX0.7EsupR9ozZ4x0dcCAGnNtUwJIP0rLdQFIy1VL4IYy_w  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": "18532968",
      "message": null
    }
    ```

### Authenticate the lecturer (2)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/auth?username=1984092420130913>
  - Headers  
    Content-Type: application/json
- Response
  - Headers  
    Auth-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuaWsiOiIxOTg0MDkyNDIwMTMwOTEzIiwiaWF0IjoxNjEwMTczMzg1fQ.zyCnKCgE59QeB1nbHGLAS84v92RjUdPvheNI2o-JCqA  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": "1984092420130913",
      "message": null
    }
    ```

### Authenticate the study program (3)

- Request
  - Endpoint  
    POST <http://localhost:3000/api/auth/study-program>
  - Headers  
    Content-Type: application/json
  - Body

    ```json
    {
      "kodeFp": "53",
      "password": "teknik_informatika"
    }
    ```

- Response
  - Headers  
    Auth-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJrb2RlRnAiOiI1MyIsIm5hbWUiOiJUZWtuaWsgSW5mb3JtYXRpa2EiLCJpYXQiOjE2MTAxNzM1MjB9.2QMAZG41BclHcIhwZPnXxXdLPnocVdm7du1bhq9utrY  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "kodeFp": "53",
        "name": "Teknik Informatika"
      },
      "message": null
    }
    ```

## ------------------- {BASE_URL}/api/mahasiswa -----------------------

### Get the details of student (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/mahasiswa?nim=20533396>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "nim": "20533396",
        "nama_mhs": "SINDY MAYNANDA MUSLIHAH",
        "alamat": "DUKUH KAPONAN II RT.1/RW.1",
        "kode_fakultas": "5",
        "kode_jurusan": "3",
        "angkatan": "2020/2021",
        "email": "sindymaynanda@gmail.com"
      },
      "message": null
    }
    ```  

### Get the details of student by itself (1)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/mahasiswa/me>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "nim": "20533396",
        "nama_mhs": "SINDY MAYNANDA MUSLIHAH",
        "alamat": "DUKUH KAPONAN II RT.1/RW.1",
        "kode_fakultas": "5",
        "kode_jurusan": "3",
        "angkatan": "2020/2021",
        "email": "sindymaynanda@gmail.com"
      },
      "message": null
    }
    ```  

### Get the list of student by taken course (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/mahasiswa/courses?kode-mata-kuliah=MWP53140&id-tahun=11&page=2&limit=10>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "list_mahasiswa": [
          {
            "id_program": 879150,
            "nim": 20533337,
            "nama_mhs": "Aldyth Fonda Rachmadani"
          },
          {
            "id_program": 879555,
            "nim": 20533274,
            "nama_mhs": "Alfi Nuriyatul Hekmaah"
          },
          {
            "id_program": 879384,
            "nim": 20533244,
            "nama_mhs": "Alief Versa Herdiansyah"
          },
          {
            "id_program": 862781,
            "nim": 16532682,
            "nama_mhs": "ANDRI TRI YULIANTO"
          },
          {
            "id_program": 878772,
            "nim": 20533386,
            "nama_mhs": "ANGGA FAJAR KUSUMA"
          },
          {
            "id_program": 879024,
            "nim": 20533321,
            "nama_mhs": "ANGGUN WILDA MILA EKASARI"
          },
          {
            "id_program": 879447,
            "nim": 20533261,
            "nama_mhs": "ANNISA AULIA WARDHANI"
          },
          {
            "id_program": 879168,
            "nim": 20533340,
            "nama_mhs": "APRILIA CAHYANTI"
          },
          {
            "id_program": 878745,
            "nim": 20533383,
            "nama_mhs": "ARDI RAHMATONI"
          },
          {
            "id_program": 879492,
            "nim": 20533266,
            "nama_mhs": "ARDITTA NUGRAHINNI"
          }
        ],
        "page_info": {
          "limit": 10,
          "page": 2,
          "page_total": 16,
          "total": 154
        }
      },
      "message": null
    }
    ```  

### Get the list of student by class code (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/mahasiswa/class?kode-kelas=53201002083240&id-tahun=11&page=1&limit=100>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "list_mahasiswa": [
          {
            "nim": "16532595",
            "nama_mhs": "ADYA YUSRON ABRORI",
            "alamat": "JL. RAMBUTAN C-10 RT 3 RW 4",
            "angkatan": "2016/2017",
            "email": null,
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "17532724",
            "nama_mhs": "AJI MIFTAQUR ROYAN",
            "alamat": "RT 34 / RW 03, DUSUN NDATENGAN ",
            "angkatan": "2017/2018",
            "email": "ajirajasa48@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532892",
            "nama_mhs": "ALIM SYUKUR APRIADI",
            "alamat": "JL.KALIMANTAN, RT.02/RW.01",
            "angkatan": "2018/2019",
            "email": "alimsyukur1505@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532993",
            "nama_mhs": "BAGAS DWI CAHYONO",
            "alamat": "JL KIAGENG MIRAH RT 02 RW 01",
            "angkatan": "2018/2019",
            "email": "bagasdwi4696@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532887",
            "nama_mhs": "BAGUS CAHYO SAPUTRO",
            "alamat": "JL. MADURA",
            "angkatan": "2018/2019",
            "email": "csbagus49@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532933",
            "nama_mhs": "DANANG PRIYO WIBOWO",
            "alamat": "JL TIRTOREJO DUSUN NGENDEL",
            "angkatan": "2018/2019",
            "email": "DANANG.MINUK28@GMAIL.COM",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532948",
            "nama_mhs": "DIAJENG PUTRI",
            "alamat": "Jalan Brigjen Katamso, RT/002, RW/002",
            "angkatan": "2018/2019",
            "email": "diajengp30@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18533008",
            "nama_mhs": "DIAN WAHYU PERMATASARI",
            "alamat": "DUSUN NGULUPAN RT 01 RW 02",
            "angkatan": "2018/2019",
            "email": "dian.wp1@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532895",
            "nama_mhs": "EDY SUCIPTO",
            "alamat": "JL MASJID RT.002 RW.001 DUSUN JABUNG II",
            "angkatan": "2018/2019",
            "email": "edy2sucipto@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532913",
            "nama_mhs": "EGIK DWI PRAYOGO",
            "alamat": "RT 04 RW 15 DUSUN KONTO",
            "angkatan": "2018/2019",
            "email": "e.dwiprayogo@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532968",
            "nama_mhs": "ERIK RIO SETIAWAN",
            "alamat": "JL. SETYA BUDI RT 01 RW 01 DUKUH BIBIS",
            "angkatan": "2018/2019",
            "email": "ERIKRIOSETIAWAN49@GMAIL.COM",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "17532733",
            "nama_mhs": "FAHRY RAJENDRA",
            "alamat": "JL ANOMAN 13",
            "angkatan": "2017/2018",
            "email": "fahryrajendra98@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18533005",
            "nama_mhs": "FERI IRAWAN",
            "alamat": "DUSUN JRAKAH RT 03 RW 01 ",
            "angkatan": "2018/2019",
            "email": "iferi855@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532992",
            "nama_mhs": "FIESTA DINA NUR FITRIA PURI",
            "alamat": "JL.ANGGUR, RT.03/RW.02, DUSUN KENITEN",
            "angkatan": "2018/2019",
            "email": null,
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "17532732",
            "nama_mhs": "HENDRI EKA RAMADAN",
            "alamat": "JL SUKOWATI RT 04 RW 02",
            "angkatan": "2017/2018",
            "email": "hendrieka270@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "17532708",
            "nama_mhs": "IVAN SUBANDI",
            "alamat": "JL. AHMAD YANI RT.02 RW.02 DUSUN NGASEM",
            "angkatan": "2017/2018",
            "email": "ivanbandi7@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18533061",
            "nama_mhs": "MEGA ALYCIA PUTRI",
            "alamat": "JL. MERAPI, RT. 01 RW. 02",
            "angkatan": "2018/2019",
            "email": "alyciamega@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18533035",
            "nama_mhs": "MOKHAMAD NURSIDIQ",
            "alamat": "JL. TANJUNG RT 03 RW 01 DUSUN SECIKAL",
            "angkatan": "2018/2019",
            "email": "sidiqcigrok@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532889",
            "nama_mhs": "NANANG HARDITA",
            "alamat": "DUSUN NGOBYOGAN RT.03/RW.05 ",
            "angkatan": "2018/2019",
            "email": "nananghardita2@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "20533306",
            "nama_mhs": "NURCAHYA BUDI MARIATI",
            "alamat": "KP. SABRANG RT.002/RW.002 ",
            "angkatan": "2020/2021",
            "email": "nurcahyanbm@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18533010",
            "nama_mhs": "OSA TANIA ZELIN GUNAWAN",
            "alamat": "JL PUTATSELAWE RT 01 RW 01 DUKUH KAUMAN",
            "angkatan": "2018/2019",
            "email": "Osatania01@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532994",
            "nama_mhs": "PANTHOM RONALIA FERYANDHO",
            "alamat": "DUSUN TAPAN RT 01 RW 01",
            "angkatan": "2018/2019",
            "email": "mbahiran77@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "20533332",
            "nama_mhs": "PUNGKY DHIANITA",
            "alamat": "JL. PUNDEN RT.16 RW.02 DUSUN KELINGAN",
            "angkatan": "2020/2021",
            "email": null,
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "17532851",
            "nama_mhs": "ROBET FIRNANDO",
            "alamat": "JL.AMD RT.01 RW.02 DUSUN BULUPAYUNG",
            "angkatan": "2017/2018",
            "email": "robertkeps98@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "17532713",
            "nama_mhs": "RURIK HAMID MASKUR",
            "alamat": "RT. 11 RW. 02 DUSUN. KARANGGAYAM",
            "angkatan": "2017/2018",
            "email": "rurikhamidmaskur@yahoo.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "17532771",
            "nama_mhs": "RYAN PERMANA PUTRA ",
            "alamat": "DS. KEBON AGUNG RT 06 RW 02",
            "angkatan": "2017/2018",
            "email": null,
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "17532754",
            "nama_mhs": "SATRIO PRIO ASMORO",
            "alamat": "JL. SELABINTANA GG. MISHIL NO 11 RT 04 RW 007",
            "angkatan": "2017/2018",
            "email": "tyoreizhaski22@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532979",
            "nama_mhs": "SHANGGA PRAHARA SAKTI MAHANANI",
            "alamat": "JL.KYAI MOJO,RT.01/RW.02, DUSUN TAMANSARI",
            "angkatan": "2018/2019",
            "email": "blindead.mea@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532880",
            "nama_mhs": "SUGENG HARIADI",
            "alamat": "DUKUH MEDANG RT 02 RW 01 ",
            "angkatan": "2018/2019",
            "email": "negrosugeng97@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "17532712",
            "nama_mhs": "SULIS SETIYAWAN",
            "alamat": "JL CENDANA NO 3 DUSUN BANGSRI",
            "angkatan": "2017/2018",
            "email": "SETYAWAN.SULIS@GMAIL.COM",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "16532598",
            "nama_mhs": "SUWANTI",
            "alamat": "JL. GATOT SUBROTO RT.01 RW.012",
            "angkatan": "2016/2017",
            "email": null,
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18533053",
            "nama_mhs": "SYLVI KHOIROTUN NI'MAH",
            "alamat": "JL. RAYA SOLO NO. 25 RT 03 RW 02",
            "angkatan": "2018/2019",
            "email": "khoirotunnn@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18533039",
            "nama_mhs": "WINDI EKA TRIATMA",
            "alamat": "RT 07 RW 05 DUSUN RINGINASRI",
            "angkatan": "2018/2019",
            "email": "ekatriatma@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18533013",
            "nama_mhs": "WISNU WARDHANA",
            "alamat": "JL.WAHID HASYIM, RT.01/RW.01",
            "angkatan": "2018/2019",
            "email": "wisnu.wadana@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532878",
            "nama_mhs": "YAYAN WAHYU ANDREAN",
            "alamat": "RT 10 RW 05 DUSUN KRAJAN",
            "angkatan": "2018/2019",
            "email": "yayanwahyu123@gmail.com ",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532922",
            "nama_mhs": "YOVIE WAHYU WIDODO",
            "alamat": "RT.02/RW.04, DUSUN SETUMBAL",
            "angkatan": "2018/2019",
            "email": "yoviejengki@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18532940",
            "nama_mhs": "YUNARKO ADI NUGROHO",
            "alamat": "JL.ALI USMAN RT 03/RW 003 DUSUN ASEM GROWONG",
            "angkatan": "2018/2019",
            "email": "Yunarkoadi44@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          },
          {
            "nim": "18533012",
            "nama_mhs": "YUSUF FERY ANAWAN SETIANA",
            "alamat": "JL. STADION TIMUR NO 1 RT 04 RW 03",
            "angkatan": "2018/2019",
            "email": "fusafery@gmail.com",
            "kode_fp": "53",
            "kode_kelas": "53201002083240"
          }
        ],
        "page_info": {
          "limit": 100,
          "page": 1,
          "page_total": 1,
          "total": "38"
        }
      },
      "message": null
    }
    ```  

## ------------------- {BASE_URL}/api/dosen -----------------------

### Get the details of lecturer (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/dosen?nik=1984080520130913>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "user_id": "210",
        "nama": "Munaji,  S.Si, M.Si",
        "alamat": "Jl. Tentrem No. 16 RT 01 RW 01 Desa/Kecamatan Balong Kab. Ponorogo",
        "email": "kangmunaji@gmail.com",
        "telp": "0853xxxxxxxx",
        "t_lahir": "Ponorogo",
        "birtdate": "1984-08-05",
        "nidn": "0705088403",
        "nik": "1984080520130913",
        "fakultas": "Fakultas Teknik",
        "prodi": "Prodi Teknik Mesin",
        "agama": "Islam",
        "kode_fp": "51"
      },
      "message": null
    }
    ```  

### Get the details of lecturer by itself (2)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/dosen/me>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "user_id": "210",
        "nama": "Munaji,  S.Si, M.Si",
        "alamat": "Jl. Tentrem No. 16 RT 01 RW 01 Desa/Kecamatan Balong Kab. Ponorogo",
        "email": "kangmunaji@gmail.com",
        "telp": "0853xxxxxxxx",
        "t_lahir": "Ponorogo",
        "birtdate": "1984-08-05",
        "nidn": "0705088403",
        "nik": "1984080520130913",
        "fakultas": "Fakultas Teknik",
        "prodi": "Prodi Teknik Mesin",
        "agama": "Islam",
        "kode_fp": "51"
      },
      "message": null
    }
    ```  

### Get the list of lecturer by study program (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/dosen/study-program?kode-fp=53>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": [
        {
          "user_id": "218",
          "nama": "Adi Fajaryanto Cobantoro, S.Kom, M.Kom",
          "alamat": "Jl. Joiranan 65B Mojorejo Taman Madiun 63139",
          "email": "adifajaryanto@umpo.ac.id",
          "telp": "0838xxxxxxxx",
          "t_lahir": "Surakarta",
          "birtdate": "1984-09-24",
          "nidn": "0724098406",
          "nik": "1984092420130913",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "138",
          "nama": "Dr. Ir. Aliyadi,  M.M., M.Kom",
          "alamat": "Kertosari Indah Blok K-10 Ponorogo",
          "email": "aliyadi1@gmail.com",
          "telp": "0823xxxxxxxx",
          "t_lahir": "Lampung",
          "birtdate": "1963-01-03",
          "nidn": "0703016301",
          "nik": "1964010319900912",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "174",
          "nama": "Andy Triyanto Pujo Raharjo, S.T., M.Kom",
          "alamat": "Jl. Dr. Cipto Mangunn Kusumo No. 69 Ponorogo",
          "email": "andytriyanto244@gmail.com",
          "telp": "0857xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1971-05-21",
          "nidn": "0721057102",
          "nik": "1971052120110113",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "175",
          "nama": "Angga Prasetyo, S.T., M.Kom",
          "alamat": "jalan ir juanda154 A Ponorogo",
          "email": "uzhumaki07@gmail.com",
          "telp": "0856xxxxxxxx",
          "t_lahir": "Situbondo",
          "birtdate": "1982-08-19",
          "nidn": "0719088202",
          "nik": "1982081920111213",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "263",
          "nama": "Arif Rahman Yusuf, M. Pd",
          "alamat": "kalpataru gang 5d no 53 malang",
          "email": "ariefrahmanyusuf89@gmail.com",
          "telp": "0812xxxxxxxx",
          "t_lahir": "Malang",
          "birtdate": "1989-05-02",
          "nidn": "0702058903",
          "nik": "1989050220160913",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "223",
          "nama": "Arin Yuli Astuti, S.Kom, M.Kom",
          "alamat": "Jln. Pramuka Gg II Mangunsuman",
          "email": "arinyuliti@gmail.com",
          "telp": "0813xxxxxxxx",
          "t_lahir": "Pacitan",
          "birtdate": "1989-07-17",
          "nidn": "",
          "nik": "1989071720130913",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "171",
          "nama": "Dr. Aslan Alwi, M.Cs",
          "alamat": "Perumahan garden family B-1, singosaren, jenangan, ponorogo",
          "email": "aslan.alwi@yahoo.co.id",
          "telp": "0853xxxxxxxx",
          "t_lahir": "Kolaka",
          "birtdate": "1972-03-24",
          "nidn": "",
          "nik": "1972032420110112",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "467",
          "nama": "Benny Mafrudi, S.Ag, M.Pd.I",
          "alamat": "Jl. Irawan No. 17 Ponorogo",
          "email": "",
          "telp": "0852xxxxxxxx",
          "t_lahir": "Sidoarjo",
          "birtdate": "1969-11-02",
          "nidn": "",
          "nik": "1969110220170914",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "352",
          "nama": "DHIYAH AYU SUSILA MURTI, M.Pd",
          "alamat": "DS. KUNTI  RT/RW 02/01 KEC. SAMPUNG PONOROGO",
          "email": "dhiahayu0491@gmail.com",
          "telp": "0852xxxxxxxx",
          "t_lahir": "PONOROGO",
          "birtdate": "1985-10-30",
          "nidn": "",
          "nik": "dhiah",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "282",
          "nama": "Dwiyono Ariyadi, S.Kom, M.Kom",
          "alamat": "Jl Soroito 6a, rt/rw 2/1",
          "email": "ayick19@gmail.com",
          "telp": "0823xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1977-09-19",
          "nidn": "0719097703",
          "nik": "1977091920160913",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "273",
          "nama": "Dyah  Mustikasari, S.T., M.Eng",
          "alamat": "Jalan Sidowaloyo RT/RW:02/02 Pendem Carat Kauman Ponorogo",
          "email": "dyah.mustikasari@gmail.com",
          "telp": "0857xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1987-10-07",
          "nidn": "0707108707",
          "nik": "1987100720160913",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "356",
          "nama": "Dyah Antarukmi Purwaningrum, S.H., M.Hum",
          "alamat": "GRIYA CITRA MANDIRI KAV. 5 RT/RW 03/03 KERTOSARI BABADAN PONOROGO",
          "email": "",
          "telp": "",
          "t_lahir": "PONOROGO",
          "birtdate": "1975-08-03",
          "nidn": "",
          "nik": "dyah",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "206",
          "nama": "Ellisia Kumalasari, S.Pd, M.Pd",
          "alamat": "Perum Pesona Bougenville No 15 RT 01/RW01 Kecamatan Ponorogo Kota Kabupaten Ponorogo",
          "email": "ell.ellisia@umpo.ac.id",
          "telp": "0852xxxxxxxx",
          "t_lahir": "Bondowoso",
          "birtdate": "1985-09-05",
          "nidn": "",
          "nik": "1985090520130913",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "269",
          "nama": "Elok Putri Nimasari, S.Pd, M.Pd",
          "alamat": "Jl. KUSUMA RT 2 RW 1 DESA TRANJANG SIMAN",
          "email": "elokputrinimasari@gmail.com",
          "telp": "0856xxxxxxxx",
          "t_lahir": "PONOROGO",
          "birtdate": "1991-05-05",
          "nidn": "0705059102",
          "nik": "1991050520160913",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "284",
          "nama": "Faisal Reza Pradhana, S.Kom",
          "alamat": "Jl Raya Ponorogo Trengalek, Dusun Bibis Rt/RW:05/03 Campurejo, Sambit",
          "email": "faisalrezapradana@gmail.com",
          "telp": "0821xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1988-12-10",
          "nidn": "",
          "nik": "faisal",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "179",
          "nama": "Fauzan Masykur, S.T., M.Kom",
          "alamat": "KRANDEGAN 4/1 KEBONSARI MADIUN",
          "email": "fauzan.art@gmail.com",
          "telp": "0857xxxxxxxx",
          "t_lahir": "Madiun",
          "birtdate": "1981-03-16",
          "nidn": "0716038101",
          "nik": "1981031620111213",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "285",
          "nama": "Fitayani Intan Pradani, S.AB., S.Kom., M.Kom",
          "alamat": "Rt/Rw 01/01, Dkh Setumbal, Desa jurug, Kec. Sooko Ponorogo",
          "email": "feeyta.intan@gmail.com",
          "telp": "0812xxxxxxxx",
          "t_lahir": "Pnorogo",
          "birtdate": "1990-01-09",
          "nidn": "",
          "nik": "1990010920180914",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "246",
          "nama": "Ghulam Asrofi Buntoro, S.T., M.Eng",
          "alamat": "Jl. Sanan RT/RW 03/01 Ds. Patihan Kidul, Kec. Siman, Kab. Ponorogo",
          "email": "ghulamasrofibuntoro@gmail.com",
          "telp": "0852xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1987-07-23",
          "nidn": "0723078702",
          "nik": "1987072320160313",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "173",
          "nama": "Dra. Ida Widaningrum, M.Kom",
          "alamat": "Jl. Letjen Suprapto Gg. 1 No. 7, Ronowijayan Siman Ponorogo",
          "email": "iwidaningrum.as@gmail.com",
          "telp": "0822xxxxxxxx",
          "t_lahir": "Subang",
          "birtdate": "1966-04-17",
          "nidn": "0717046601",
          "nik": "1966041720110113",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "280",
          "nama": "Indah Puji Astuti, S.Kom, M.Kom",
          "alamat": "JL. Raya Pacitan No 327 Dengok Madusari Siman Ponorogo",
          "email": "indahsan.0912@gmail.com",
          "telp": "0852xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1986-04-24",
          "nidn": "0724048605",
          "nik": "1986042420160913",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "445",
          "nama": "Ismail Abdurrozzaq Zulkarnain, S.Kom, M.Kom",
          "alamat": "Jl. Pilangsari no.42 Rt.02 Rw.02 Kel. Purbosuman Kec. Ponorogo",
          "email": "iizzuel@gmail.com",
          "telp": "0813xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1988-07-28",
          "nidn": "",
          "nik": "1988072820180413",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "283",
          "nama": "Jamilah Karaman, S.Kom., M.Kom.",
          "alamat": "Jl Kalimantan 109 Rt/Rw:003/001 Desa Semanding Kauman",
          "email": "jamilahkaraman90@gmail.com",
          "telp": "0812xxxxxxxx",
          "t_lahir": "Sumenep",
          "birtdate": "1990-03-22",
          "nidn": "",
          "nik": "1990032220190913",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "446",
          "nama": "Khoiru Nurfitri, S.Kom, M.Kom",
          "alamat": "Dsn. Kajang, Ds. Purwosari, Kec. Babadan, Kab. Ponorogo",
          "email": "nurfitrikhoiru9@gmail.com",
          "telp": "0877xxxxxxxx",
          "t_lahir": "Pacitan",
          "birtdate": "1992-04-30",
          "nidn": "",
          "nik": "1992043020180813",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "525",
          "nama": "Moh Reza Syaifur Rizal S.Kom., M.Kom.",
          "alamat": "Jalan Jawa Perumahaman Jasmin No14, Ponorogo",
          "email": "",
          "telp": "",
          "t_lahir": "Ponorogo",
          "birtdate": "1991-07-25",
          "nidn": "",
          "nik": "mohreza20",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "216",
          "nama": "Mohammad Bhanu Setyawan, S.T., M.Kom",
          "alamat": "Jl. Kalimantan No. 58 Ds. Semanding Kec. Kauman Ponorogo",
          "email": "mohammad.setyawan@gmail.com",
          "telp": "0812xxxxxxxx",
          "t_lahir": "Sampang",
          "birtdate": "1980-02-25",
          "nidn": "0725028002",
          "nik": "1980022520130913",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "164",
          "nama": "Munirah  S.Kom, M.T.",
          "alamat": "Perumahan Garden Family Blok B No.16, Ponorogo",
          "email": "munirah.mt@gmail.com",
          "telp": "0852xxxxxxxx",
          "t_lahir": "Jakarta",
          "birtdate": "1979-11-07",
          "nidn": "0907117910",
          "nik": "1979110720091212",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "277",
          "nama": "Nurwanto,  S.Kom, M.Kom",
          "alamat": "Ds. Karanganyar RT. 02 RW. 01 Kec.Reban Kab.Batang, Jawa Tengah, 51273",
          "email": "noeng.hunter@gmail.com",
          "telp": "0816xxxxxxxx",
          "t_lahir": "Batang",
          "birtdate": "1987-12-04",
          "nidn": "0704128703",
          "nik": "1987120420180813",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "519",
          "nama": "Rifqi Rahmatika Az-Zahra S.Kom., M.Kom.",
          "alamat": "Jl. Pramuka gg2 A/3 RT/RW 004/003 Ponorogo",
          "email": "rifqizahra31@gmail.com",
          "telp": "0812xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1993-10-31",
          "nidn": "",
          "nik": "rifqi_rahmatika",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "404",
          "nama": "Ritus Nur Armada, S.Psi",
          "alamat": "",
          "email": "",
          "telp": "0812xxxxxxxx",
          "t_lahir": "Trenggalek",
          "birtdate": "1984-01-22",
          "nidn": "",
          "nik": "ritus",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "145",
          "nama": "Drs. Rudianto,  M.Ag",
          "alamat": "Jl. Lejend. Suprapto II/8b Ponorogo",
          "email": "alrujikar@gmail.com",
          "telp": "0812xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1964-04-15",
          "nidn": "0715046402",
          "nik": "1964041519960912",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "380",
          "nama": "Drs. Sudarmani,  M.M.",
          "alamat": "Jl Menur 1 B Rt 03 / Rw 03 Kel/Desa ; Nologaten Ponorogo",
          "email": "",
          "telp": "0812xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1951-06-18",
          "nidn": "",
          "nik": "1951061820160914",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "172",
          "nama": "Sugianti,  S.Si, M.Kom",
          "alamat": "Jl. Veteran No. 1 Surodikraman Ponorogo",
          "email": "sugiantisetyawan@ymail.com",
          "telp": "0856xxxxxxxx",
          "t_lahir": "Ponorogo",
          "birtdate": "1978-05-05",
          "nidn": "0705057803",
          "nik": "1978050520110113",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "276",
          "nama": "Ulya Mardiani, S.Pd",
          "alamat": "Perum Kertosari estate D.40 Kertosari, Babadan,Ponorogo",
          "email": "ulya_hckeeper77@ymail.com",
          "telp": "0856xxxxxxxx",
          "t_lahir": "Gunung Kidul",
          "birtdate": "1989-09-29",
          "nidn": "",
          "nik": "ulya",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        },
        {
          "user_id": "207",
          "nama": "Yovi Litanianda, S.Pd, M.Kom",
          "alamat": "jl. H P kusuma 1 no 1 ponorogo",
          "email": "yoviumpo@gmail.com",
          "telp": "484333",
          "t_lahir": "Bogor",
          "birtdate": "1981-02-21",
          "nidn": "0721028102",
          "nik": "1981022120081014",
          "fakultas": "Fakultas Teknik",
          "prodi": "Prodi Teknik Informatika",
          "agama": "Islam",
          "kode_fp": "53"
        }
      ],
      "message": null
    }
    ```  

## ------------------- {BASE_URL}/api/jurusan -----------------------

### Get the list of study program (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/jurusan>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": [
        {
          "kode_fp": "51",
          "nama_jurusan": "Teknik Mesin"
        },
        {
          "kode_fp": "52",
          "nama_jurusan": "Teknik Elektro"
        },
        {
          "kode_fp": "53",
          "nama_jurusan": "Teknik Informatika"
        }
      ],
      "message": null
    }
    ```  

### Get the details of study program by itself (3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/jurusan/me>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "kodeFp": "53",
        "name": "Teknik Informatika"
      },
      "message": null
    }
    ```  

### Get the details of study program (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/jurusan/53>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "kodeFp": "53",
        "name": "Teknik Informatika"
      },
      "message": null
    }
    ```  

### Change the study program password (2)

- Request
  - Endpoint  
    PUT <http://localhost:3000/api/jurusan/change-password>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}
  - Body

    ```json
    {
      "password": "new_password"
    }
    ```  

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": "Password changed successfully.",
      "message": null
    }
    ```  

## ------------------- {BASE_URL}/api/semester -----------------------

### Get the list of semester (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/semester>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": [
        {
          "id_thn": "1",
          "tahun": "2015",
          "smtr_teks": "Ganjil",
          "stts_kuliah": "0"
        },
        {
          "id_thn": "2",
          "tahun": "2015",
          "smtr_teks": "Genap",
          "stts_kuliah": "0"
        },
        {
          "id_thn": "3",
          "tahun": "2016",
          "smtr_teks": "Ganjil",
          "stts_kuliah": "0"
        },
        {
          "id_thn": "4",
          "tahun": "2016",
          "smtr_teks": "Genap",
          "stts_kuliah": "0"
        },
        {
          "id_thn": "5",
          "tahun": "2017",
          "smtr_teks": "Ganjil",
          "stts_kuliah": "0"
        },
        {
          "id_thn": "6",
          "tahun": "2017",
          "smtr_teks": "Genap",
          "stts_kuliah": "0"
        },
        {
          "id_thn": "7",
          "tahun": "2018",
          "smtr_teks": "Ganjil",
          "stts_kuliah": "0"
        },
        {
          "id_thn": "8",
          "tahun": "2018",
          "smtr_teks": "Genap",
          "stts_kuliah": "0"
        },
        {
          "id_thn": "9",
          "tahun": "2019",
          "smtr_teks": "Ganjil",
          "stts_kuliah": "0"
        },
        {
          "id_thn": "10",
          "tahun": "2019",
          "smtr_teks": "Genap",
          "stts_kuliah": "0"
        },
        {
          "id_thn": "11",
          "tahun": "2020",
          "smtr_teks": "Ganjil",
          "stts_kuliah": "1"
        }
      ],
      "message": null
    }
    ```  

### Get active semester (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/semester/active>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "id_thn": "11",
        "tahun": "2020",
        "smtr_teks": "Ganjil",
        "stts_kuliah": "1"
      },
      "message": null
    }
    ```  

## ------------------- {BASE_URL}/api/krs -----------------------

### Get the student taken courses (1)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/krs?id-tahun=11>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": [
        {
          "id_program": "879951",
          "kode_mk2": "MWP53109",
          "nama_mk": "Logika Matematika"
        },
        {
          "id_program": "879952",
          "kode_mk2": "MWP53136",
          "nama_mk": "Praktikum Peng.Teknologi Informatika"
        },
        {
          "id_program": "879950",
          "kode_mk2": "MWP53105",
          "nama_mk": "Arsitektur dan Organisasi Komputer"
        },
        {
          "id_program": "879949",
          "kode_mk2": "MWP53103",
          "nama_mk": "Algoritma dan Struktur Data"
        },
        {
          "id_program": "879944",
          "kode_mk2": "MWU53101",
          "nama_mk": "Agama Islam"
        },
        {
          "id_program": "879945",
          "kode_mk2": "MWU53105",
          "nama_mk": "Bahasa Inggris"
        },
        {
          "id_program": "879946",
          "kode_mk2": "MWU53102",
          "nama_mk": "Bahasa Indonesia"
        },
        {
          "id_program": "879947",
          "kode_mk2": "MWP53101",
          "nama_mk": "Pengantar Teknologi Informasi"
        },
        {
          "id_program": "879948",
          "kode_mk2": "MWP53102",
          "nama_mk": "Kalkulus"
        }
      ],
      "message": null
    }
    ```  

## ------------------- {BASE_URL}/api/jadwal -----------------------

### Get the schedule (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/jadwal?kode-mata-kuliah=MWP53140&id-tahun=11>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": [
        {
          "kelas": "A",
          "hari": "Selasa",
          "jam": "14.10 - 15.00",
          "nama_ruang": "F505",
          "kode_fp": "53",
          "nama_dosen": " Nurwanto,  S.Kom, M.Kom",
          "kode_kelas": "53201002082552"
        },
        {
          "kelas": "B",
          "hari": "Jumat",
          "jam": "14.10 - 15.00",
          "nama_ruang": "F507",
          "kode_fp": "53",
          "nama_dosen": " Indah Puji Astuti, S.Kom, M.Kom",
          "kode_kelas": "53201002082651"
        },
        {
          "kelas": "C",
          "hari": "Jumat",
          "jam": "14.10 - 15.00",
          "nama_ruang": "F508",
          "kode_fp": "53",
          "nama_dosen": " Andy Triyanto Pujo Raharjo, S.T., M.Kom",
          "kode_kelas": "53201002082957"
        },
        {
          "kelas": "D",
          "hari": "Jumat",
          "jam": "15.30 - 16.20",
          "nama_ruang": "F505",
          "kode_fp": "53",
          "nama_dosen": " Dwiyono Ariyadi, S.Kom, M.Kom",
          "kode_kelas": "53201002083057"
        },
        {
          "kelas": "E",
          "hari": "Jumat",
          "jam": "15.30 - 16.20",
          "nama_ruang": "F507",
          "kode_fp": "53",
          "nama_dosen": " Rifqi Rahmatika Az-Zahra S.Kom., M.Kom.",
          "kode_kelas": "53201002083158"
        },
        {
          "kelas": "Khusus",
          "hari": "Jumat",
          "jam": "15.30 - 16.20",
          "nama_ruang": "F508",
          "kode_fp": "53",
          "nama_dosen": " Adi Fajaryanto Cobantoro, S.Kom, M.Kom",
          "kode_kelas": "53201002083240"
        }
      ],
      "message": null
    }
    ```  

## ------------------- {BASE_URL}/api/praktikum -----------------------

### Get the list of practice (1, 2, 3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/praktikum>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": [
        {
          "kodeFp": "53",
          "kodeMk": "MWP53136",
          "namaMk": "Praktikum Peng. Teknologi Informatika",
          "smtrTeks": "Ganjil",
          "fee": 450000
        },
        {
          "kodeFp": "53",
          "kodeMk": "MWP53138",
          "namaMk": "Praktikum Sistem Basis Data",
          "smtrTeks": "Ganjil",
          "fee": 200000
        },
        {
          "kodeFp": "53",
          "kodeMk": "MWP53140",
          "namaMk": "Praktikum Pemrog. Perangkat Lunak",
          "smtrTeks": "Ganjil",
          "fee": 200000
        },
        {
          "kodeFp": "53",
          "kodeMk": "MWP53142",
          "namaMk": "Praktikum Sistem Cerdas",
          "smtrTeks": "Ganjil",
          "fee": 200000
        },
        {
          "kodeFp": "53",
          "kodeMk": "MWP53237",
          "namaMk": "Praktikum Pemrog. Berorientasi Obyek",
          "smtrTeks": "Genap",
          "fee": 200000
        },
        {
          "kodeFp": "53",
          "kodeMk": "MWP53239",
          "namaMk": "Praktikum Jaringan",
          "smtrTeks": "Genap",
          "fee": 200000
        },
        {
          "kodeFp": "53",
          "kodeMk": "MWP53241",
          "namaMk": "Praktikum Pemrograman Multimedia",
          "smtrTeks": "Genap",
          "fee": 200000
        }
      ],
      "message": null
    }
    ```  

### Get the list of available practice (1)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/praktikum/available?id-tahun=11>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": [
        {
          "kodeFp": "53",
          "kodeMk": "MWP53136",
          "namaMk": "Praktikum Peng. Teknologi Informatika",
          "smtrTeks": "Ganjil",
          "fee": 450000
        }
      ],
      "message": null
    }
    ```  

### Register the practice (1)

- Request
  - Endpoint  
    POST <http://localhost:3000/api/praktikum/register?kode-mata-kuliah=MWP53136>
  - Headers  
    Content-Type: multipart/form-data  
    Auth-Token: {GENERATED TOKEN}  
    Content-Dispotion: form-data; name="practicepayment"; filename="bukti-pembayaran-praktikum.png"

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": "Register success.",
      "message": null
    }
    ```  

### Get the practice register status (1)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/praktikum/register/status?kode-mata-kuliah=MWP53136&id-tahun=11>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN} 

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "nim": 20533396,
        "kodeMk": "MWP53136",
        "namaMk": "Praktikum Peng. Teknologi Informatika",
        "IdThn": 11,
        "status": "Verified",
        "tglDaftar": "2021-02-03T13:35:19.000Z",
        "buktiPembayaran": "practicepayment/2021-02-03T06:28:15.219Z-practicepayment-974868e8bbeeba0f29a63cd60a88bc80-20533396.png"
      },
      "message": null
    }
    ```  

### Get the practice register list (1)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/praktikum/register/list?id-tahun=11>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
        "status": "success",
        "data": [
          {
            "nim": 20533396,
            "kodeMk": "MWP53136",
            "namaMk": "Praktikum Peng. Teknologi Informatika",
            "IdThn": 11,
            "status": "Verified",
            "tglDaftar": "2021-02-03T13:35:19.000Z",
            "buktiPembayaran": "practicepayment/2021-02-03T06:28:15.219Z-practicepayment-974868e8bbeeba0f29a63cd60a88bc80-20533396.png"
          }
        ],
        "message": null
    }
    ```  

### Upload the practice report (1)

- Request
  - Endpoint  
    POST <http://localhost:3000/api/praktikum/report?kode-mata-kuliah=MWP53136&id-tahun=11&kd-kelas=53201002082957>
  - Headers  
    Content-Type: multipart/form-data  
    Auth-Token: {GENERATED TOKEN}  
    Content-Dispotion: form-data; name="practicereport"; filename="erikriosetiawan-laporan-praktikum.pdf"

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": "File submitted successfully.",
      "message": null
    }
    ```  

### Get the details of practice report (1)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/praktikum/report?kode-mata-kuliah=MWP53136&id-tahun=11>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": {
        "id": 4,
        "nim": 20533396,
        "kdKelas": "53201002082957",
        "idThn": 11,
        "kodeMk": "MWP53136",
        "file": "practicereport/2021-01-10T14:17:07.289Z-practicereport-97db328ffd74fe561741c0b9f37a4cda-20533396.pdf",
        "tglSubmit": "2021-01-10T14:17:07.000Z",
        "status": "Review"
      },
      "message": null
    }
    ```  

### Update the practice report (1)

- Request
  - Endpoint  
    PUT <http://localhost:3000/api/praktikum/report/4>
  - Headers  
    Content-Type: multipart/form-data  
    Auth-Token: {GENERATED TOKEN}  
    Content-Dispotion: form-data; name="practicereport"; filename="erikriosetiawan-laporan-praktikum.pdf"

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": "File updated successfully.",
      "message": null
    }
    ```  

### Post the practice report comment (2)

- Request
  - Endpoint  
    POST <http://localhost:3000/api/praktikum/comments?laporan-praktikum-id=4>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}
  - Body

    ```json
    {
      "comments": "Laporan praktikum sudah bagus dan sesuai"
    }
    ```  

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": "Comments added succesfully.",
      "message": null
    }
    ```  

### Get the practice report comments (1, 2)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/praktikum/comments?laporan-praktikum-id=4>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": [
        {
          "id": 2,
          "idLaporanPraktikum": 4,
          "nik": "1984092420130913",
          "name": "Munaji,  S.Si, M.Si",
          "komentar": "Laporan praktikum sudah bagus dan sesuai",
          "tglKomentar": "2021-01-11T12:13:11.000Z"
        },
        {
          "id": 3,
          "idLaporanPraktikum": 4,
          "nik": "1984092420130913",
          "name": "Munaji,  S.Si, M.Si",
          "komentar": "Kamu dapat nilai A",
          "tglKomentar": "2021-01-11T12:13:56.000Z"
        }
      ],
      "message": null
    }
    ```  

### Add the practice financial report (3)

- Request
  - Endpoint  
    POST <http://localhost:3000/api/praktikum/practice-financial-report?id-tahun=11>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}
  - Body

    ```json
    {
      "informasi": "Pembelian alat praktikum",
      "tipe": "Debit",
      "nominal": 3000000
    }
    ```  

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": "Practice financial report added succesfully.",
      "message": null
    }
    ```  

### Get the list of practice financial report (3)

- Request
  - Endpoint  
    GET <http://localhost:3000/api/praktikum/practice-financial-report?id-tahun=11>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": [
        {
          "id": 1,
          "kodeFp": "53",
          "idThn": 11,
          "tahun": "2020",
          "smtrTeks": "Ganjil",
          "tanggal": "2021-01-12T05:44:15.000Z",
          "informasi": "Pembelian alat praktikum dan pencetakan modul",
          "tipe": "Debit",
          "nominal": 4500000
        }
      ],
      "message": null
    }
    ```  

### Update the practice financial report (3)

- Request
  - Endpoint  
    PUT <http://localhost:3000/api/praktikum/practice-financial-report/1>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}
  - Body

    ```json
    {
      "informasi": "Pembelian alat praktikum dan pencetakan modul",
      "tipe": "Credit",
      "nominal": 4500000
    }
    ```  

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": "Practice financial report updated succesfully.",
      "message": null
    }
    ```  

### Delete the practice financial report (3)

- Request
  - Endpoint  
    DELETE <http://localhost:3000/api/praktikum/practice-financial-report/2>
  - Headers  
    Content-Type: application/json  
    Auth-Token: {GENERATED TOKEN}

- Response
  - Headers  
    Content-Type: application/json; charset=utf-8
  - Body

    ```json
    {
      "status": "success",
      "data": "Practice financial report deleted succesfully.",
      "message": null
    }
    ```  
