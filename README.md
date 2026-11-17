# POMi · Releases

Canal de distribuição da aplicação Android **POMi**.

Este repositório contém apenas os ficheiros de instalação (APK) e o manifesto
de versões que a aplicação consulta para se atualizar. O código-fonte é
mantido num repositório privado.

## Instalação

1. Descarregar o APK mais recente em [Releases](../../releases/latest).
2. Abrir o ficheiro no telemóvel e, se o Android pedir, autorizar a
   instalação a partir desta origem.

A partir daí, a aplicação avisa quando houver uma versão nova e instala-a
sem ser preciso voltar aqui.

## Conteúdo

| Ficheiro                   | Descrição                                          |
| -------------------------- | -------------------------------------------------- |
| `version.json`             | Manifesto com a versão atual, lido pela aplicação. |
| [Releases](../../releases) | APKs de cada versão, identificados pela tag.       |

## Manifesto `version.json`

```json
{
  "versionCode": 5,
  "versionName": "0.8.0",
  "apkUrl": "https://github.com/FSDinvest/pomi-releases/releases/download/v0.8.0/POMi-v0.8.0.apk",
  "changelog": "Uma novidade por linha.\nOutra novidade.",
  "forceUpdate": false
}
```

| Campo         | Descrição                                                                     |
| ------------- | ----------------------------------------------------------------------------- |
| `versionCode` | Número inteiro da versão. A aplicação só se atualiza se este valor for maior. |
| `versionName` | Versão apresentada ao utilizador (ex. `0.8.0`).                               |
| `apkUrl`      | Endereço `https://` do APK anexado à release.                                 |
| `changelog`   | Novidades da versão, uma por linha.                                           |
| `forceUpdate` | Se `true`, a atualização é obrigatória e o aviso não pode ser fechado.        |

## Publicar uma versão

1. Criar uma release com a tag da versão (ex. `v0.8.0`) e anexar o APK
   assinado, com o nome `POMi-v<versão>.apk`.
2. Atualizar o `version.json`. O `versionCode` tem de ser igual ao do APK
   anexado.
3. Fazer commit no ramo `main`.

A versão fica disponível logo após o commit. O processo completo está
descrito em `docs/Atualizacoes_App.md`, no repositório da aplicação.

> [!IMPORTANT]
> As aplicações instaladas leem o `version.json` diretamente do ramo `main`.
> Não mudar o nome do ficheiro nem do ramo.
