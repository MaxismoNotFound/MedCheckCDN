# %product% API

_NOTA: Per utilizzare l'API di %product%, è necessario possedere un chiave di licenza valida ARTIC Softworks, attivabile tramite ARTIC License Helper._

# **Ottenere un file di licenza valido**
Per ottenere un file di licenza valido per l'utilizzo dell'API di %product%, è necessario aprire ARTIC License Helper e selezionare l'opzione <shortcut>2</shortcut> e seguire le istruzioni visualizzate per generare un file di licenza.<br>Una volta ottenuto il file di licenza, è necessario inserirlo nella cartella <shortcut>data</shortcut> del vostro programma.

# **Importazione dell'API**
Per importare le funzioni dell'API di %product%, è necessario fare riferimento al file  <shortcut>libMedCheckAPI.dll</shortcut>.<br><br>Questo è un esempio in C#:
<code-block>
            [DllImport("libMedCheckAPI.dll", CallingConvention = CallingConvention.Cdecl)]
            public static extern IntPtr singleFileProcedure(string pdfName);
            [DllImport("libMedCheckAPI.dll", CallingConvention = CallingConvention.Cdecl)]
            public static extern IntPtr multiFileProcedure(string autoPath);
</code-block>

# **Codifica di un file**

<tabs>
    <tab title="Singolo file">
        Per codificare un singolo file PDF, è necessario fare riferimento alla funzione <shortcut>singleFileProcedure</shortcut> del DLL.<br>Questo è un esempio in C#:<br>
        <code-block>
            IntPtr outputPtr = singleFileProcedure(filePath);
            string output = Marshal.PtrToStringAnsi(outputPtr);
        </code-block>
    </tab>
    <tab title="Più file">
        Per codificare più file PDF contenuti nella cartella <shortcut>AUTO</shortcut>, è necessario fare riferimento alla funzione <shortcut>multiFileProcedure</shortcut> del DLL.<br>Questo è un esempio in C#:<br>
        <code-block>
            IntPtr outputPtr = multiFileProcedure(filePath);
            string output = Marshal.PtrToStringAnsi(outputPtr);
        </code-block>
    </tab>
</tabs>