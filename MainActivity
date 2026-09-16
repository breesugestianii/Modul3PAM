package com.example.pemesanantiket

import android.content.Intent
import android.net.Uri
import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.layout.*
import androidx.compose.material.icons.Icons
import androidx.compose.material.icons.filled.Email
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import androidx.compose.ui.platform.LocalContext
import com.example.pemesanantiket.ui.theme.PemesananTiketTheme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        setContent {
            PemesananTiketTheme {
                TicketScreen()
            }
        }
    }
}

@Composable
fun TicketScreen() {
    val context = LocalContext.current
    val hargaTiket = 15000

    var jumlahTiket by remember {
        mutableStateOf(1)
    }

    val totalBayar = hargaTiket * jumlahTiket

    Column(
        modifier = Modifier
            .fillMaxSize()
            .padding(24.dp),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.Center
    ) {

        Text(
            text = "Pemesanan Tiket Kereta",
            fontSize = 26.sp,
            fontWeight = FontWeight.Bold
        )

        Spacer(modifier = Modifier.height(20.dp))

        Card(
            modifier = Modifier.fillMaxWidth()
        ) {
            Column(
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(20.dp),
                horizontalAlignment = Alignment.CenterHorizontally
            ) {

                Text(
                    text = "Malang → Papar",
                    fontSize = 22.sp,
                    fontWeight = FontWeight.Bold
                )

                Spacer(modifier = Modifier.height(12.dp))

                Text(
                    text = "Rp15.000 / tiket"
                )

                Spacer(modifier = Modifier.height(16.dp))

                Text(
                    text = "Jumlah Tiket",
                    fontWeight = FontWeight.Bold
                )

                Row(
                    verticalAlignment = Alignment.CenterVertically
                ) {

                    Button(
                        onClick = {
                            if (jumlahTiket > 1) {
                                jumlahTiket--
                            }
                        }
                    ) {
                        Text("-")
                    }

                    Text(
                        text = "$jumlahTiket",
                        fontSize = 22.sp,
                        fontWeight = FontWeight.Bold,
                        modifier = Modifier.padding(horizontal = 24.dp)
                    )

                    Button(
                        onClick = {
                            jumlahTiket++
                        }
                    ) {
                        Text("+")
                    }
                }

                Spacer(modifier = Modifier.height(16.dp))

                Text(
                    text = "Total: Rp$totalBayar",
                    fontSize = 20.sp,
                    fontWeight = FontWeight.Bold
                )
            }
        }

        Spacer(modifier = Modifier.height(20.dp))

        Button(
            onClick = {
                val intent = Intent(Intent.ACTION_SENDTO).apply {
                    data = Uri.parse("mailto:test@gmail.com")
                }

                context.startActivity(
                    Intent.createChooser(
                        intent,
                        "Pilih aplikasi email"
                    )
                )
            },
            modifier = Modifier.fillMaxWidth()
        ) {

            Icon(
                imageVector = Icons.Default.Email,
                contentDescription = "Email"
            )

            Spacer(modifier = Modifier.width(8.dp))

            Text("Konfirmasi Pesanan")
        }

        Spacer(modifier = Modifier.height(8.dp))

        OutlinedButton(
            onClick = {
                jumlahTiket = 1
            },
            modifier = Modifier.fillMaxWidth()
        ) {
            Text("Reset")
        }
    }
}
