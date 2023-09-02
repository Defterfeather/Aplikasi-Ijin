<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    
    <title>Bootstrap demo</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-4bw+/aepP/YC94hEpVNVgiZdgIC5+VKNBQNGCHeKRQN+PtmoHDEXuppvnDJzQIu9" crossorigin="anonymous">
  </head>
  <body>
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
        <div class="container-fluid">
          <a class="navbar-brand" href="#">Navbar</a>
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNavDropdown">
            <ul class="navbar-nav">
              <li class="nav-item">
                <a class="nav-link active" aria-current="page" href="#">Home</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">Features</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">Pricing</a>
              </li>
              <li class="nav-item dropdown">
                <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                  Dropdown link
                </a>
                <ul class="dropdown-menu">
                  <li><a class="dropdown-item" href="#">Action</a></li>
                  <li><a class="dropdown-item" href="#">Another action</a></li>
                  <li><a class="dropdown-item" href="#">Something else here</a></li>
                </ul>
              </li>
            </ul>
          </div>
        </div>
      </nav>
      <div class="container mt-4">
        <h2 class="my-5">aplikasi ijin kelas XI-RPl</h2>
        <div class="alert alert-success alert-dismissible fade show my-alert d-none" role="alert">
            <strong>terima kasih!</strong> data permohonan ijin telah berhasil diterima.
            <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
          </div>
        <form class="row " name="proses-ijin">
            <div class="col-md-4">
                <label for="kelas" class="form-label">plih kelas</label>
                <select class="form-select" name="kelas" required>
                    <option selected>-PILIH KELAS-</option>
                    <option value="XI-RPL">XI-RPL</option>
                  </select>
            </div>
            <div class="col-md-4 mb-4">
                <label for="nama" class="form-label">Nama Siswa</label>
                <select class="form-select" name="nama" required>
                    <option selected>- NAMA SISWA -</option>
                    <option value="ANDI NAUVAL ZACKY">ANDI NAUVAL ZACKY</option>
                    <option value="RENDY">RENDY</option>
                    <option value="Ahyan">Ahyan</option>
                    <option value="Dhika">Dhika</option>
                    <option value="Athaya">Athaya</option>
                    <option value="Iki">IKi</option>
                    <option value="Gilang">Gilang</option>
                    <option value="Mahes">Mahes</option>
                </select>
            </div>
            <div class="col-md-4 mb-4">
                <label for="nama" class="form-label">NIS</label>
                <select class="form-select" name="nis" required>
                    <option selected>- NIS -</option>
                    <option value="66978">66978</option>
                    <option value="66759">66759</option>
                </select>
            </div>
           
            <div class="col-md-4 mb-4">
                <label for="tgl" class="form-label mb-3">Tanggal</label>
                <input type="date" id="tgl" class="form-control" name="tanggal" required>
            </div>

            <label for="keterangan" class="form-label">keterangan ijin</label>
            <div class="btn-group" role="group" aria-label="Basic radio toggle button group">
                <input type="radio" class="btn-check" name="keterangan" id="keterangan1" autocomplete="off" value="keperluan keluarga">
                <label class="btn btn-outline-primary" for="keterangan1">Keperluan keluarga</label>
              
                <input type="radio" class="btn-check" name="keterangan" id="keterangan2" autocomplete="off" value="sakit">
                <label class="btn btn-outline-primary" for="keterangan2">sakit</label>
              
                <input type="radio" class="btn-check" name="keterangan" id="keterangan3" autocomplete="off" value="terlambat">
                <label class="btn btn-outline-primary" for="keterangan3">terlambat</label>
              </div>

            <div class="col-8">
              <label for="alasan" class="form-label">alasan tidak masuk/ijin/terlambat</label>
              <input type="text" class="form-control" id="inputAddress" name="alasan" autocomplete="off">
            </div>
            
            
            <div class="col-12 mt-4">
                <button type="submit" class="btn btn-outline-primary btn-kirim">Kirim Data</button>
                <button class="btn btn-primary btn-loading d-none" type="button" disabled>
                    <span class="spinner-grow spinner-grow-sm" aria-hidden="true"></span>
                    <span role="status">Loading...</span>
                  </button>
            </div>
          </form>
      </div>

    

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/js/bootstrap.bundle.min.js" integrity="sha384-HwwvtgBNo3bZJJLYd8oVXjrBZt8cqVSpeBNS5n7C8IVInixGAoxmnlMuBnhbgrkm" crossorigin="anonymous"></script>
    <script>
        const scriptURL = 'https://script.google.com/macros/s/AKfycby6AUpSLKl2SZdqwB-Y1QXPlN3XJv-Sec739Okrxw6VI0X8qGI4HWxlT9d-erDjk-c/exec'
        const form = document.forms['proses-ijin']
        const btnKirim = document.querySelector('.btn-kirim');
        const btnLoading = document.querySelector('.btn-loading');
        const myAlert = document.querySelector('.my-alert');


        
        form.addEventListener('submit', e => {
            e.preventDefault()

            btnLoading.classList.toggle('d-none');
            btnKirim.classList.toggle('d-none');

          fetch(scriptURL, { method: 'POST', body: new FormData(form)})
            .then(response => {

                btnLoading.classList.toggle('d-none');
                btnKirim.classList.toggle('d-none');

                myAlert.classList.toggle('d-none');
                form.reset();

                console.log('Success!', response);

             })
            

            .catch(error => console.error('Error!', error.message));
        })
      </script>
</body>
</html>

