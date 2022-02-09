---
title: Skype 會議室系統和商務用 Skype 同盟協力廠商
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 閱讀此主題以瞭解如何設定商務用 Skype 同盟協力廠商的 Skype 會議室系統。
ms.openlocfilehash: dc725acfce7e2d55758b3074df538d69ead0d6a1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399997"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 會議室系統和商務用 Skype 同盟協力廠商
 
閱讀此主題以瞭解如何設定商務用 Skype 同盟協力廠商的 Skype 會議室系統。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 會議室系統和商務用 Skype 同盟協力廠商

Skype 房間系統依賴行事曆會議邀請中的加入商務用 Skype 會議連結。 在會議邀請中，通常會找到匯合連結。 不過，Skype 的會議室系統取決於此連結會出現在郵件的 MAPI 屬性中。 將此會議要求傳送給遠端組織時 (商務用 Skype 同盟夥伴) 時，預設會在該遠端組織 Skype 的會議室系統不會在行事曆上顯示會議加入連結。 實際上，遠端組織中的任何 Outlook 使用者都無法使用滑鼠右鍵按一下行事曆專案或從會議提醒內，加入商務用 Skype 會議。 他們必須開啟會議邀請，然後按一下郵件本文中的 [加入商務用 Skype 會議]。 
  
這種限制的原因是 Outlook 和 Microsoft Exchange 不使用特殊的方法來封裝資訊，以便在網際網路上傳送郵件。 這種方法稱為傳輸中性封裝格式 (TNEF) ，預設為從 Exchange 組織外部傳送的郵件停用。 若要讓會議加入連結出現在遠端 Skype 的會議室系統上，傳送組織必須使用下列命令來啟用 TNEF：
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

針對遠端組織啟用 TNEF 後，透過網際網路傳送給組織的任何郵件都會以 TNEF 格式的附件形式傳送。 在啟用 TNEF 的情況下，當商務用 Skype 會議要求傳送給商務用 Skype 同盟協力廠商時，Skype 的會議室系統會能夠轉譯加入商務用 Skype 會議，而遠端使用者將可以加入商務用 Skype 會議。 
