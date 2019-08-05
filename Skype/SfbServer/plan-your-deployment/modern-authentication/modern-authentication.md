---
title: 在商務用 Skype 中規劃新式驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 規劃商務用 Skype Server 的驗證及授權主題, 包括與其他產品的整合
ms.openlocfilehash: 922b53b26bd77be4f7d49e7c594d337f7961703d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192981"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>在商務用 Skype 中討論驗證與授權

驗證與授權是相關概念, 但對您執行不同的工作 (雖然這兩者都是必要的)。 以簡單的詞彙為 authenciation (AuthN), 只會根據機密使用者知道或擁有的密碼, 也可以是密碼、代碼、指紋、憑證、聲明關於使用者的宣告組合, 或是共同使用這些專案的組合。 AuthN 是一個處理常式, 可以證明您是自己所說的人。

授權 (AuthZ) 與您驗證您的身份之後, 就會與您有權存取的專案相關。 它會判斷您已允許查看、編輯及以其他方式存取的專案。 例如, 您可能具備 SharePoint Online 的強大網站集合管理員存取權, 但如果您切換到另一個線上工作負載 (例如商務用 Skype Online), 您可能有權對使用者問題進行疑難排解, 而不會變更其設定伺服器或伺服器。 在第三個工作負荷 (例如 Exchange Online) 中, 您可能只會擁有一般使用者的存取權。 AuthZ 會檢查您對服務/worloads、應用程式、檔案及其他資料所擁有的存取權。

我們的範例涉及 SharePoint 和 Exchange online 等線上屬性, 但 AuthN 和 AuthZ 的處理常式在內部部署及混合式部署中都是相同的。 最後, 諸如 AAD Connect 和 ADFS 之類的工具, 只要將內部部署帳戶和密碼同步處理到雲端的廣告 (在 Office 365 或 Azure 中則是 Azure AD), 或是在授權流程中 intruding, 就能讓使用者通常不會收到其認證的提示, 比如說, 在雲端中切換工作負載時, 建立單一登入案例。 但它們本身不是由責任 AuthN 或 AuthZ 所組成, 只是其中一個機制。

今天, 許多技術會將這些程式 (AuthN 和 AuthZ) 視為單一機制, 而且您會聽到許多對驗證程式的參考, 也就是在其中加入授權。 請務必記住, 使用者存取中的第一個步驟是 AuthN, 證明您是誰所說的人員, 而且該 AuthZ 人員會使用使用者決定有權存取權的人員 (如您在開啟授權或 OAuth 中所看到的內容)。

  
## <a name="authentication-and-authorization-planning-topics"></a>驗證與授權規劃主題

[如何在商務用 Skype 中使用新式驗證 (ADAL)](plan-adal.md)

[現代驗證支援的商務用 Skype 拓撲](topologies-supported.md)

[規劃在內部和外部將舊版驗證方法關閉至您的網路。](turn-on-modern-auth.md)

