# API

API Data PetaBencana menyediakan sejumlah endpoint untuk Anda dapat berinteraksi dengan sistem. Ringkasan di bawah ini adalah detail lengkap dari setiap endpoint dan contoh hasil permintaan dapat ditemukan di halaman berikutnya.

## Ringkasan _Endpoint_

Detail dari setiap endpoint adalah sebagai berikut:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Endpoint</th>
      <th style="text-align:left">Deskripsi</th>
      <th style="text-align:left">Metode</th>
      <th style="text-align:left">Terproteksi</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">/cards</td>
      <td style="text-align:left">Kartu Laporan</td>
      <td style="text-align:left">GET,PUT</td>
      <td style="text-align:left">Ya</td>
    </tr>
    <tr>
      <td style="text-align:left">/admin</td>
      <td style="text-align:left">Batas Administrasi</td>
      <td style="text-align:left">GET</td>
      <td style="text-align:left">Tidak</td>
    </tr>
    <tr>
      <td style="text-align:left">/feeds</td>
      <td style="text-align:left">Umpan</td>
      <td style="text-align:left">GET,PUT</td>
      <td style="text-align:left">Ya</td>
    </tr>
    <tr>
      <td style="text-align:left">/floodgauges</td>
      <td style="text-align:left">
        <p>Alat Ukur Tinggi</p>
        <p>Muka Air</p>
      </td>
      <td style="text-align:left">GET,PUT</td>
      <td style="text-align:left">Tidak</td>
    </tr>
    <tr>
      <td style="text-align:left">/floods</td>
      <td style="text-align:left">Genangan Banjir</td>
      <td style="text-align:left">GET</td>
      <td style="text-align:left">Sebagian</td>
    </tr>
    <tr>
      <td style="text-align:left">/floods/archive</td>
      <td style="text-align:left">Arsip Genangan Banjir</td>
      <td style="text-align:left">GET</td>
      <td style="text-align:left">Tidak</td>
    </tr>
    <tr>
      <td style="text-align:left">/floods/timeseries</td>
      <td style="text-align:left">
        <p>Time Series</p>
        <p>Genangan Banjir</p>
      </td>
      <td style="text-align:left">GET</td>
      <td style="text-align:left">Tidak</td>
    </tr>
    <tr>
      <td style="text-align:left">/infrastructure</td>
      <td style="text-align:left">Infrastruktur</td>
      <td style="text-align:left">GET</td>
      <td style="text-align:left">Tidak</td>
    </tr>
    <tr>
      <td style="text-align:left">/reports</td>
      <td style="text-align:left">Laporan Urun-daya</td>
      <td style="text-align:left">GET</td>
      <td style="text-align:left">Tidak</td>
    </tr>
    <tr>
      <td style="text-align:left">/reports/archive</td>
      <td style="text-align:left">
        <p>Arsip Laporan</p>
        <p>Urun-daya</p>
      </td>
      <td style="text-align:left">GET</td>
      <td style="text-align:left">Tidak</td>
    </tr>
    <tr>
      <td style="text-align:left">/reports/timeseries</td>
      <td style="text-align:left">
        <p>Time Series Laporan</p>
        <p>Urun-daya</p>
      </td>
      <td style="text-align:left">GET</td>
      <td style="text-align:left">Tidak</td>
    </tr>
    <tr>
      <td style="text-align:left">/stats/*</td>
      <td style="text-align:left">Statistik Ringkasan</td>
      <td style="text-align:left">GET</td>
      <td style="text-align:left">Tidak</td>
    </tr>
  </tbody>
</table>

