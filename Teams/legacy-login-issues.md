---
title: 在 Teams 中舊版系統接收訊息和通話時發生問題
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
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
description: 針對在舊版系統上接收訊息和通話的相關問題進行疑難排解
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56499af9534c3559cdfa3311a360caa60d06d3d7
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789518"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>在舊版系統上接收訊息和通話時發生問題

如果使用者使用舊版 Teams 或使用其他應用程式登入，使用者可能會收到訊息或來電時發生問題。

## <a name="legacy-adu-setups"></a>舊版 ADU 設定

 如果使用者登入加入網域的電腦，但是您 **不希望 Teams 登入畫面預先填入其使用者名稱**，系統管理員可以設定下列 Windows 登錄，關閉預先填入使用者名稱 (UPN) 的功能：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> 針對以「.local」或「.corp」結尾的使用者名稱，略過或忽略使用者名稱預先填入的功能預設為開啟，因此您不需要設定登錄機碼就能關閉預先填入。

如需詳細資訊，請參閱 [使用新式驗證登入 Microsoft Teams](sign-in-teams.md) 。

## <a name="skype-token-revocation"></a>Skype 權杖吊銷

變更/重設密碼時，舊版用戶端最多一小時都不會收到訊息和來電。 若要解決此問題，請重新開機應用程式或移至較新的用戶端。


## <a name="related-topics"></a>相關主題

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)