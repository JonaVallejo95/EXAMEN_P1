ESTE CODIGO CONSTA DE DOS ACTIVITY Y CON ESTE CODIGO PUEDES  REALIZAR LA PROGRAMACION DE UNA SUMA
package com.example.suma2numerosam

import android.content.Intent
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import android.view.View

class calculo : AppCompatActivity() {
    lateinit var edtNum1: EditText
    lateinit var edtNum2 : EditText
    lateinit var btnSumar : Button
    lateinit var txtresultado : TextView

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_calculo)
        val edittext1: TextView = findViewById(R.id.txt_respuesta)

        edtNum1 = findViewById(R.id.txt_n1)
        edtNum2 = findViewById(R.id.txt_n2)
        btnSumar = findViewById(R.id.btn_suma)
        txtresultado = findViewById(R.id.txt_respuesta)

        btnSumar.setOnClickListener(View.OnClickListener   {

            try {

                val num1 = Integer.parseInt(edtNum1.text.toString())
                val num2 = Integer.parseInt(edtNum2.text.toString())
                txtresultado.setText("resultado: " + sumar(num1, num2))
            }catch (ex: Exception){}
            val message:String = edittext1.text.toString()
            val sendMessage = Intent(this, resultadoActivity2::class.java)
            sendMessage.putExtra("EXTRA_MESSAGE", message )
            startActivity(sendMessage)
        })

    }
    fun sumar (numero1: Int, numero2: Int): Int {

        return numero1 + numero2
    }
}
