# Atlas-AI1.0

## Gerar APK de teste

O arquivo `atlas-google-login-fixed.zip` contém os arquivos de um app Android já compilado, não o projeto-fonte. O workflow empacota esses arquivos, alinha o APK e assina uma versão de teste; ele não recompila nem altera o app.

No GitHub, abra **Actions > Package debug APK > Run workflow**. Ao terminar, baixe o artifact `atlas-google-login-debug-apk` na execução.

Por padrão, cada execução cria uma chave de depuração temporária. Para manter uma assinatura estável (necessária para atualizar a instalação sem desinstalar e normalmente para configurar o login Google), adicione estes secrets ao repositório antes de executar:

- `ANDROID_KEYSTORE_BASE64`: keystore codificado em Base64.
- `ANDROID_KEYSTORE_PASSWORD`: senha do keystore.
- `ANDROID_KEY_ALIAS`: alias da chave.
- `ANDROID_KEY_PASSWORD`: senha da chave.

Uma assinatura de depuração não é adequada para publicar na Play Store. Para distribuição, use uma chave de lançamento protegida e valide a configuração OAuth do app com o fingerprint dessa chave.