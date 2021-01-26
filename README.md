# Calculadora_Android_Java
## Integrantes:
- Miguel Torres 
- Freddy Calahorrano
A continuación se muestra una calculadora realizada en android y su explicación:

## Diseño de la interface:
Para el diseño de interface se estructuro mediante Gridlayauts el orden y tamaños de los botones, ademas de el area de texto en donde se mostrará tanto el resultado como los numeros 
seleccionados por el usuario.
de esta manera:

```python
<GridLayout
            android:id="@+id/gridLayout"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentStart="true"
            android:layout_alignParentBottom="true"
            android:layout_gravity="center"
            android:columnCount="4"
            android:orientation="horizontal"
            android:padding="0dp"
            android:rowCount="6">

            <Button
                android:id="@+id/Clean"
                android:layout_margin="2dp"
                android:background="#424242"
                android:text="C"
                android:textColor="#FF5722" />

            <Button
                android:id="@+id/Divide"
                android:layout_margin="2dp"
                android:background="#424242"
                android:text="/"
                android:textColor="#FF5722" />
.
.
.
/>
```
## Lógica
Para la lógica se uso JAVA y aqui definimos lo que va a realizar la calculadora:
<br/>Todo eso lo podra ralizar por medio de los operasdores definidos y se ejecutarán cuando se presione el boton **Igual(=)**, el mismo que contendra una sentencia **If**, a continuacion se muestra algunas
porciones de codigo de la lógica:

```python
btnSuma.setOnClickListener(new View.OnClickListener(){
            public void onClick(View v){
                reserva = Resultado.getText().toString();
                operador = "+";
                Resultado.setText("");
            }
        });

        btnResta.setOnClickListener(new View.OnClickListener(){
            public void onClick(View v){
                reserva = Resultado.getText().toString();
                operador = "-";
                Resultado.setText("");
            }
        });

        btnMultiplica.setOnClickListener(new View.OnClickListener(){
            public void onClick(View v){
                reserva = Resultado.getText().toString();
                operador = "*";
                Resultado.setText("");
            }
        });

        btnDivide.setOnClickListener(new View.OnClickListener(){
            public void onClick(View v){
                reserva = Resultado.getText().toString();
                operador = "/";
                Resultado.setText("");
            }
        });

        btnPunto.setOnClickListener(new View.OnClickListener(){
            public void onClick(View v){
                mostrar = Resultado.getText().toString();
                mostrar = mostrar + ".";
                Resultado.setText(mostrar);
            }
        });

        btnClean.setOnClickListener(new View.OnClickListener(){
            public void onClick(View v){
                mostrar = "";
                Resultado.setText(mostrar);
                reserva = "";
                operador = "";
            }
        });

        btnBorrar.setOnClickListener(new View.OnClickListener(){
            public void onClick(View v){
                mostrar = Resultado.getText().toString();
                mostrar = mostrar.substring(0,mostrar.length()-1);
                Resultado.setText(mostrar);
            }
        });

/>
```
Y el boton **Igual**:

```python
 btnIgual.setOnClickListener(new View.OnClickListener(){
            public void onClick(View v){
                mostrar = Resultado.getText().toString();
                mostrar = mostrar + "1";
                if(operador.equals("-")){
                    resultado = Double.parseDouble(reserva) - Double.parseDouble(Resultado.getText().toString());
                    Resultado.setText(String.valueOf(resultado));
                }
                if(operador.equals("+")){
                    resultado = Double.parseDouble(reserva) + Double.parseDouble(Resultado.getText().toString());
                    Resultado.setText(String.valueOf(resultado));
                }
                if(operador.equals("/")){
                    resultado = Double.parseDouble(reserva) / Double.parseDouble(Resultado.getText().toString());
                    Resultado.setText(String.valueOf(resultado));
                }
                if(operador.equals("*")){
                    resultado = Double.parseDouble(reserva) * Double.parseDouble(Resultado.getText().toString());
                    Resultado.setText(String.valueOf(resultado));
                }
            }
        });
```

