---
title: 在團隊中接收有關舊版系統的訊息和通話問題
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
description: 針對在舊版系統上接收郵件與通話的相關問題進行疑難排解
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52038470e81b825391e4176c07af7a30f51356df
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489156"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>在舊版系統上接收郵件和通話的問題
==============================================================

如果使用者使用的是較舊版本的小組，或已使用其他應用程式登入，就可能會遇到接收郵件或呼叫的問題。

## <a name="legacy-adu-setups"></a>舊版 ADU 設置

 如果使用者登入加入網域的電腦，但是您**不希望 Teams 登入畫面預先填入其使用者名稱**，系統管理員可以設定下列 Windows 登錄，關閉預先填入使用者名稱 (UPN) 的功能：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> 針對以 ".local" 或 ".corp" 結尾的使用者名稱，略過或忽略使用者名稱預先填入的功能依預設會開啟，因此您不需要設定登錄機碼就能關閉此功能。

如需詳細資訊，請參閱[使用新式驗證登入 Microsoft 團隊](sign-in-teams.md)。

## <a name="skype-token-revocation"></a>Skype 權杖吊銷

在變更/重設密碼時，舊版用戶端將不會收到長達一小時的訊息和來電。 若要解決此問題，請重新開機應用程式或移至較新的用戶端。