| Nama       | Risky HariAdi                  |
| ---------- | ------------------------------ |
| NIM        | 312010124                      |
| Kelas      | TI.20.RPL-1                    |
| Mata Kuliah| Pemrograman Visual             |
| Dosen      | Agung Nugroho, S.Kom., M.Kom.  |

## Latihan
# 1. Program Menghitung Gaji Karyawan

<li>Tampilan Utama Program</li></br>

![foto](foto/Slide1.PNG)</p>

<li>Menghitung Gaji Bersih Direktur Tetap</li></br>

![foto](foto/1.png)</p>

<li>Menghitung Gaji Bersih Manager Tetap</li></br>

![foto](foto/2.png)</p>

<li>Menghitung Gaji Bersih Karyawan Tetap</li></br>

![foto](foto/3.png)</p>

<li>Menghitung Gaji Bersih Direktur Honorer</li></br>

![foto](foto/11.png)</p>

<li>Menghitung Gaji Bersih Manager Honorer</li></br>

![foto](foto/22.png)</p>

<li>Menghitung Gaji Bersih Karyawan Honorer</li></br>

![foto](foto/33.png)</p>

<li>Full Source Code Programnya</li></br>

```pascal

unit Unit1;

{$mode objfpc}{$H+}

interface

uses
  Classes, SysUtils, Forms, Controls, Graphics, Dialogs, StdCtrls, ExtCtrls;

type

  { TForm1 }

  TForm1 = class(TForm)
    btnHitung: TButton;
    btnIsiData: TButton;
    btnClose: TButton;
    cbJabatan: TComboBox;
    edtTotalGaji: TEdit;
    edtTunjangan: TEdit;
    edtGapok: TEdit;
    edtNama: TEdit;
    Label1: TLabel;
    Label2: TLabel;
    Label3: TLabel;
    Label4: TLabel;
    Label5: TLabel;
    rbHonorer: TRadioButton;
    rbTetap: TRadioButton;
    rgStatus: TRadioGroup;
    procedure btnHitungClick(Sender: TObject);
    procedure cbJabatanChange(Sender: TObject);
    procedure rbHonorerChange(Sender: TObject);
    procedure rbTetapChange(Sender: TObject);
    procedure rgStatusClick(Sender: TObject);
  private

  public

  end;

var
  Form1: TForm1;

implementation

{$R *.lfm}

{ TForm1 }

procedure TForm1.rbHonorerChange(Sender: TObject);
begin
  if rbHonorer.Checked then
    edtTunjangan.Caption := '500000';

end;

procedure TForm1.rbTetapChange(Sender: TObject);
begin
  if rbTetap.Checked then
    edtTunjangan.Caption := '1500000';
end;

procedure TForm1.rgStatusClick(Sender: TObject);
begin


end;

procedure TForm1.btnHitungClick(Sender: TObject);
var
  GajiPokok, TotalGaji, GajiBersih: Double;
  StatusTunjangan: Double;


begin
  GajiPokok := StrToFloat(edtGapok.Text);
  StatusTunjangan := StrToFloat(edtTunjangan.Text);

  TotalGaji := GajiPokok + StatusTunjangan;

  GajiBersih := TotalGaji;

  edtTotalGaji.Text := FormatFloat('#,##0.00', TotalGaji);

end;

procedure TForm1.cbJabatanChange(Sender: TObject);
var
  Jabatan: string;
  GajiPokok: Double;

begin
  Jabatan := cbJabatan.Items[cbJabatan.ItemIndex];

  case Jabatan of
    'Direktur': GajiPokok := 5000000;
    'Manager': GajiPokok := 3000000;
    'Karyawan': GajiPokok := 1000000;
  else
    GajiPokok := 0; // Nilai default jika jabatan tidak ada
  end;

  edtGapok.Text := FloatToStr(GajiPokok);
end;

end.

end;

end.

end;

end;

end.


```