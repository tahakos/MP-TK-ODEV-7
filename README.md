# MP-TK-ODEV-3

package com.example.myapplication;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

public class MainActivity extends AppCompatActivity{

Intent intent = getIntent();
String data = intent.getStringExtra(“Key”);

buildFeatures{
 viewBinding true
}

private ActivityMainBinding binding;
@Override
protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 binding = ActivityMainBinding.inflate(getLayoutInflater());
 View view = binding.getRoot();
 setContentView(view);
}

public void digerActivity(View view){
 String adiSoyadi = binding.editTextTextAdiSoyadi.getText().toString();
 String telefonNo = binding.editTextTelefon.getText().toString();
 Intent intent = new Intent(MainActivity.this,BilgiActivity.class);
 intent.putExtra(“adiSoyadiKey”,adiSoyadi);
 intent.putExtra(“telefonNoKey”,telefonNo);
 startActivity(intent);
}

private ActivityBilgiBinding binding;
@Override
protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 binding = ActivityBilgiBinding.inflate(getLayoutInflater());
 View view = binding.getRoot();
 setContentView(view);
}

private ActivityBilgiBinding binding;
@Override
protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 binding = ActivityBilgiBinding.inflate(getLayoutInflater());
 View view = binding.getRoot();
 setContentView(view);
 Intent intent = getIntent();
 String bilgiAdiSoyadi = intent.getStringExtra(“adiSoyadiKey”);
 String bilgiTelefonNo = intent.getStringExtra(“telefonNoKey”);
 binding.textViewAdiSoyadi.setText(bilgiAdiSoyadi);
 binding.textViewTelefonNo.setText(bilgiTelefonNo);
}
Public class Singleton{
//Tanımlanacak değişkenler
private static Singleton singleton;
	 //private şeklinde bir constuctor
	 //public türünde getter ve setter
public static Singleton getInstance(){
 if (singleton==null){
 singleton = new Singleton();
 }
return singleton;
}
}
