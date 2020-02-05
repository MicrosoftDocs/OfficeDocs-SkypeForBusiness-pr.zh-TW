---
title: Skype 房間系統和商務用 Skype 聯盟合作夥伴
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 請閱讀本主題，瞭解如何針對商務用 Skype 同盟合作夥伴設定 Skype 會議室系統。
ms.openlocfilehash: d5ee83857aa439791e2a31ef201e0f365dbb8408
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768716"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 房間系統和商務用 Skype 聯盟合作夥伴
 
請閱讀本主題，瞭解如何針對商務用 Skype 同盟合作夥伴設定 Skype 會議室系統。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 房間系統和商務用 Skype 聯盟合作夥伴

Skype 會議室系統依賴行事曆會議邀請中的 [加入商務用 Skype 會議] 連結。 加入連結通常是在會議邀請內文中找到。 不過，Skype 房間系統依賴此連結，就會出現在郵件的 MAPI 屬性中。 當此會議邀請傳送至遠端組織（商務用 Skype 同盟合作夥伴）時，預設情況下，遠端組織的 Skype 會議室系統不會顯示行事曆上的 [會議加入] 連結。 事實上，遠端組織中的任何 Outlook 使用者都無法以滑鼠右鍵按一下行事曆專案或從會議提醒中加入商務用 Skype 會議。 他們必須開啟會議邀請，然後按一下郵件本文中的 [加入商務用 Skype 會議]。 
  
這個限制的原因是 Outlook 和 Microsoft Exchange 不使用特殊的方法封裝資訊，以便在網際網路上傳送郵件。 此方法稱為 [傳輸中性封裝格式（TNEF）]，預設為從 Exchange 組織外部傳送的郵件停用。 若要在遠端 Skype 聊天室系統上顯示會議加入連結，傳送組織必須使用下列命令來啟用 TNEF：
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

在遠端組織啟用 TNEF 之後，透過網際網路傳送的任何郵件都會以 TNEF 格式的附件傳送給組織。 在已啟用 TNEF 的情況下，當商務用 skype 會議邀請傳送到商務用 Skype 同盟合作夥伴時，Skype 室系統將能夠轉譯商務用 skype 會議，而遠端使用者將能夠加入商務用 Skype 會議。 
