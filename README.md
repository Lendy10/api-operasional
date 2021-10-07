# api-operasional
Contains user documentation on how to use SOFIA API

SOFIA is a college integrated educational system built by Department of Physics, Universitas Airlangga. Universaly, this system is ready to be scaled both horizontally and vertically to accomodate every single events that take place on college environment. By helicopter view, SOFIA facilitates 3 objectives: Teaching, Audit, and Student Affair.

There are full documentations for developers for this particular project, but because of the sensitivity of the data we can't publish it publicly, otherwise if you are interested on our system you may contact us via available social media. We are very pleased to be able to work together. In this document, we are going to explain the usage of SOFIA API for presence recapitulation, extended document might be published in the future.

<h1>Registration</h1>

<h2>HTTP Request</h2>

```json
POST https://operasional.fisika.fst.unair.ac.id/api/register
```

<h2>Request Body</h2>

```json
{
    "username": "string",
    "email": "{your valid email}",
    "password": "{your password}"
}
```

<h2>Response Body</h2>

if successfull, the response body will contains a timely expire JWT. Further read about JWT can be found <a href="https://jwt.io/introduction">here</a>. The token on the response have to be used for every request you make, for now you already can make a request to SOFIA. But, in case you forget the token, you always can retrieve the new one by executing Login event. Please be mindful with your password because it needed for login.

<h1>Login</h1>

<h2>HTTP Request</h2>

```json
GET https://operasional.fisika.fst.unair.ac.id/api/login
```

<h2>Request Body</h2>

```json
{
    "username": "{your username}",
    "password": "{your password}"
}
```
if successfull, the response body will contains a timely expire JWT.

<h1>Rekapitulasi presensi Matkul By Student NIM</h1>

<h2>HTTP Request</h2>

```json
GET https://operasional.fisika.fst.unair.ac.id/api/rekapitulasi_presensi_mahasiswa
```

<h2>Request Body</h2>

```json
{
    "token": "{your JWT}",
    "NIM": "{Intended Student}"
}
```
if successfull, the response body will contains the information associated with the student presence data on current particular study of semester. One instance of request is as follow

```json
{
            "KD_Matkul": "FIT206",
            "Nama_Kelas": "B1",
            "Meeting": "7",
            "Hadir": "6",
            "Tidak_Hadir": "1",
            "Nama_Matkul": "Fisika Gelombang",
            "Detail_pertemuan": [
                {
                    "pertemuan_ke": "1",
                    "tgl_perkuliahan": "Tuesday, 07 September 2021",
                    "jam_mulai_perkuliahan": "09:00:27",
                    "jam_selesai_perkuliahan": "09:02:27"
                },
            ]
}
```

<h1>Rekapitulasi presensi Matkul By Mata Kuliah ID</h1>

<h2>HTTP Request</h2>

```json
GET https://operasional.fisika.fst.unair.ac.id/api/rekapitulasi_presensi_matkul
```

<h2>Request Body</h2>

```json
{
    "token": "{your JWT}",
    "KD_Matkul": "{Intended Course}",
    "NM_Kelas": "{Course Class}"
}
```
if successfull, the response body will contains the information associated with the course presence recapitulation on current active study of semester. One instance of request is as follow

```json
{
 "Detail_mahasiswa": [
        {
            "NIM": "77723323",
            "Nama": "John Doe",
            "HADIR": "3",
            "TIDAK_HADIR": "5",
            "MEETING": "8",
            "Prosentase": "37.5%"
        },
      ],
 "Detail_pertemuan": [
        {
            "pertemuan_ke": "1",
            "tgl_perkuliahan": "Monday, 06 September 2021",
            "jam_mulai_perkuliahan": "09:23:53",
            "jam_selesai_perkuliahan": "10:15:35"
        }
      ]
}
```



