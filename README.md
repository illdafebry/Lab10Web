# Praktikum 10

Illda Febryawan Budiono - 311910749 - TI.19.A.2

### LANGKAH-LANGKAH
#### 1. Buka XAMPP, aktifkan Apache dan MySQL
![1](https://user-images.githubusercontent.com/85242560/120922444-62179f80-c6f3-11eb-8bab-f1e5065a5dac.png)
#### 2. Buat folder `lab9_php_oop` pada root directory web server `(d:\xampp\htdocs)`
![2](https://user-images.githubusercontent.com/85242560/120922461-76f43300-c6f3-11eb-9d43-cee39e28d62f.png)
#### 3. Buat file baru dengan nama `mobil.php` sebagai contoh PHP OOP sederhana
* coding
```
<?php
/**
* Program sederhana pendefinisian class dan pemanggilan class.
**/

class Mobil
{
    private $warna;
    private $merk;
    private $harga;

    public function __construct()
    {
    $this->warna = "Biru";
    $this->merk = "BMW";
    $this->harga = "10000000";
    }

    public function gantiWarna ($warnaBaru)
    {
    $this->warna = $warnaBaru;
    }

    public function tampilWarna ()
    {
    echo "Warna mobilnya : " . $this->warna;
    }
}
// membuat objek mobil
$a = new Mobil();
$b = new Mobil();

// memanggil objek
echo "<b>Mobil pertama</b><br>";
$a->tampilWarna();
echo "<br>Mobil pertama ganti warna<br>";
$a->gantiWarna("Merah");
$a->tampilWarna();

// memanggil objek
echo "<br><b>Mobil kedua</b><br>";
$b->gantiWarna("Hijau");
$b->tampilWarna();

?>
```
![3 coding 1](https://user-images.githubusercontent.com/85242560/120922503-ba4ea180-c6f3-11eb-8246-9497b2c387b8.png)
![3 coding 2](https://user-images.githubusercontent.com/85242560/120922504-bcb0fb80-c6f3-11eb-8d1a-26d6589b045e.png)
* output
![3 hasilnya](https://user-images.githubusercontent.com/85242560/120922506-c3d80980-c6f3-11eb-8400-96e2c87b4b13.png)
#### 4. Buat file baru dengan nama `form.php` sebagai Class
* coding
```
<?php
/**
* Nama Class: Form
* Deskripsi: CLass untuk membuat form inputan text sederhana
**/

class Form
{
    private $fields = array();
    private $action;
    private $submit = "Submit Form";
    private $jumField = 0;

    public function __construct($action, $submit)
    {
    $this->action = $action;
    $this->submit = $submit;
    }
    
    public function displayForm()
    {
    echo "<form action='".$this->action."' method='POST'>";
    echo '<table width="100%" border="0">';
    for ($j=0; $j<count($this->fields); $j++) {
        echo "<tr><td align='right'>".$this->fields[$j]['label']."</td>";
        echo "<td><input type='text' name='".$this->fields[$j]['name']."'></td></tr>";
        }
        echo "<tr><td colspan='2'>";
        echo "<input type='submit' value='".$this->submit."'></td></tr>";
        echo "</table>";
    }

    public function addField($name, $label)
    {
        $this->fields [$this->jumField]['name'] = $name;
        $this->fields [$this->jumField]['label'] = $label;
        $this->jumField ++;
    }
}

?>
```
![4 coding 1](https://user-images.githubusercontent.com/85242560/120922531-f6820200-c6f3-11eb-85e0-f6511cf2875a.png)
![4 coding 2](https://user-images.githubusercontent.com/85242560/120922534-f84bc580-c6f3-11eb-9a4b-80fc8d345712.png)
#### 5. 4. Buat file baru dengan nama `form_input.php` untuk memanggil Class `form.php`
* coding
```
<?php
/**
* Program memanfaatkan Program 10.2 untuk membuat form inputan sederhana.
**/

include "form.php";

echo "<html><head><title>Mahasiswa</title></head><body>";
$form = new Form("","Input Form");
$form->addField("txtnim", "Nim");
$form->addField("txtnama", "Nama");
$form->addField("txtalamat", "Alamat");
echo "<h3>Silahkan isi form berikut ini :</h3>";
$form->displayForm();
echo "</body></html>";

?>
```
![5 coding](https://user-images.githubusercontent.com/85242560/120922642-8e7feb80-c6f4-11eb-9be8-1c4d84701da2.png)
* output
![5 hasilnya](https://user-images.githubusercontent.com/85242560/120922646-93dd3600-c6f4-11eb-96df-8e044fb6056c.png)
