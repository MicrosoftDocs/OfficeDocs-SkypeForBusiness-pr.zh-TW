---
title: 在舊版系統上接收訊息和通話時Teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 針對在舊版系統上接收訊息和通話相關問題進行疑難排解
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b013817ab363b91f7041d285616f7bd919dc84b9afd1298ec74d8e9dc64046a5
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848378"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>在舊版系統上接收訊息和通話的問題

如果使用者使用舊版的手機或已與其他應用程式Teams，則接收郵件或通話時可能有問題。

## <a name="legacy-adu-setups"></a>舊版 ADU 設定

 如果使用者登入加入網域的電腦，但是您 **不希望 Teams 登入畫面預先填入其使用者名稱**，系統管理員可以設定下列 Windows 登錄，關閉預先填入使用者名稱 (UPN) 的功能：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> 針對以「.local」或「.corp」結尾的使用者名稱，略過或忽略使用者名稱預先填入的功能預設為開啟，因此您不需要設定登錄機碼就能關閉預先填入。

請參閱[使用新式驗證Microsoft Teams以使用新式](sign-in-teams.md)驗證來驗證，以瞭解更多資訊。

## <a name="skype-token-revocation"></a>Skype權杖吊銷

變更/重設密碼時，較舊的用戶端最多一小時不會收到訊息和通話。 若要解決此問題，請重新開機應用程式或移至較新的用戶端。


## <a name="related-topics"></a>相關主題

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)