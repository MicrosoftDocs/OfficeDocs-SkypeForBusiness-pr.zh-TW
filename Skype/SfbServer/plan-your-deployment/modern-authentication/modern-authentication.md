---
title: 在商務用 Skype 中規劃新式驗證
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 規劃商務用 Skype Server 驗證及授權的主題，包括與其他產品的整合
ms.openlocfilehash: a0d9e8dff4a08c670ce2af0b6eb9399146cef006
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632677"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>在商務用 Skype 中討論驗證和授權

驗證和授權是相關的概念，但為您 (，雖然兩者都是必要) 。 放入簡易的字詞中，authenciation (AuthN) 取決於機密有效的使用者只知道或具備，而且可以是密碼、程式碼、指紋、憑證、有關使用者的宣告組合，或是這些專案一起使用的組合。 AuthN 是一種可證明您是否為您所說的使用者的處理常式。

授權 (AuthZ) 與您驗證您的人選後，與您可以存取的內容相關。 它會決定您已允許查看、編輯或以其他方式存取的專案。 例如，您可能有功能強大的網站集合管理員存取權 SharePoint 線上，但是如果您切換到另一個線上工作負載（如商務用 Skype online），您可能會具備疑難排解使用者問題的許可權，而不會變更伺服器或伺服器的設定。 在第三個工作負載中，例如 Exchange Online，您可能只會具備平均使用者的存取權。 AuthZ 會檢查您對服務/worloads、應用程式、檔案及其他資料的存取權。

我們的範例包括 SharePoint 和 Exchange 線上等線上屬性，但是 AuthN 和 AuthZ 的處理常式會以相同的方式，在內部部署和混合式部署中運作。 最後，像 AAD 連線和 ADFS 之類 AuthN 的工具，可透過將內部部署帳戶和密碼同步處理至雲端的 AD (（Azure AD) 或授權流程中的 intruding），以將內部部署帳戶和密碼同步處理至雲端的 AD （例如，在雲端中切換工作負載時，建立單一 Sign-On 案例）。 不過，他們本身不負責 AuthN 或 AuthZ，只是部分機制。

目前，許多技術會考慮這些程式 (AuthN 和 AuthZ) 為一種機制，您也會聽到許多驗證程式的參考，也就是在其中包含授權。 請務必記住，使用者存取中的第一步是 AuthN，證明您是由您所說的，而該 AuthZ 人員會使用他們的知識來決定誰可以存取 (，如您將會看到開啟的授權或 OAuth) 。

  
## <a name="authentication-and-authorization-planning-topics"></a>驗證和授權規劃主題

[如何搭配商務用 Skype 使用新式驗證 (ADAL) ](plan-adal.md)

[新式驗證支援的商務用 Skype 拓撲](topologies-supported.md)

[規劃在內部和外部關閉舊版驗證方法。](turn-on-modern-auth.md)

