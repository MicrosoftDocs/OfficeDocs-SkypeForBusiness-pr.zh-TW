---
title: 團隊語音 Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多國企業的小組語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785973"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 案例研究：自動語音應答及呼叫佇列

Contoso 已熟悉自動語音應答及從其內部部署商務用 Skype 部署呼叫佇列。 若要瞭解如何設定雲端自動語音應答，他們[會複習什麼是雲端自動](what-are-phone-system-auto-attendants.md)語音應答？以及[小型企業範例-設定自動助理教學](tutorial-org-aa.yml)課程。 若要瞭解設定通話佇列的可用選項，Contoso 已審閱 [[建立雲端通話佇列](create-a-phone-system-call-queue.md)]。  

## <a name="requirements-depending-on-site-type"></a>根據網站類型而定的需求

視網站類型而定，Contoso 有下列需求：

- 網站類型 A：傳統舊版電話系統 

  [網站類型] 您需要將與接待員相關聯的電話號碼保留為其自動語音應答的號碼。 每個網站的主要部門都要有自己的通話佇列，以傳送給小組成員。 有一個混合的網站，可將手機系統與直接路由與電話系統搭配通話方案使用。  

- 網站類型 B：商務用 Skype 企業語音 

  網站類型 B 有現有的自動語音應答及呼叫佇列，需要將它遷移至小組。 Contoso 需要保留與自動語音助理相關聯的電話號碼。 Contoso 已使用通話方案將大部分這些網站移至電話系統。 不過，在幾個無法使用通話方案的位置，Contoso 會將這些網站移至直接路由設定。  

- 網站類型 C：商務用 Skype Enterprise Voice & 傳統舊版電話系統 

  網站類型 C 已有駐留在傳統舊版電話系統中的自動語音應答。 此網站的決定與設定與 [網站類型 A] 相同。   

- 針對所有網站類型，Contoso 提出下列問題：

  - 問：我們會使用新的或現有的號碼嗎？ 
    A： Contoso 決定將現有的電話號碼指派給自動語音應答的服務帳戶。 

  - 問：自動語音應答會在何時可接受來電？ 
    A： Contoso 決定要設定上班時間，並在上班時間已重新導向至「下班後」自動語音應答之後收到來電。  

  - 問：如何將呼叫路由到通話佇列中的成員： [助理]、[串列] 或 [迴圈複用] 路由？ 
    A： Contoso 決定使用助理路由， 

  - 問：我們如何判斷使用者應該何時或不應該撥打電話？ 
    A： Contoso 決定使用 [呼叫處理] 選項來判斷是否有可用的代理程式：目前狀態路由。 


## <a name="configuration"></a>Configuration

設定自動語音應答及呼叫佇列的步驟，包括以下在[管理資源帳戶](manage-resource-accounts.md)中所述的下列各項： 

1. 取得服務號碼。 

2. 取得免費的電話系統-虛擬使用者授權或付費電話系統授權，以與資源帳戶或電話系統授權搭配使用。

3. 建立資源帳戶。 需要自動語音應答或通話佇列，才能擁有關聯的資源帳戶。 

4. 將電話系統或電話系統-虛擬使用者授權指派給資源帳戶。 如需詳細資訊，請參閱[Microsoft 365 電話系統-虛擬使用者授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)。

5. 將服務電話號碼指派給您指派授權的資源帳戶。 

6. 建立電話系統通話佇列或自動語音應答 

7. 連結資源帳戶與通話佇列或自動語音應答。 


### <a name="sites-with-phone-system-with-direct-routing"></a>具有直接路由的手機系統網站 

Contoso 必須將當地電信公司提供的電話號碼設定為 Office 365 中的服務號碼。 

- 若要設定透過直接路由提供的電話號碼，Contoso 按照 [[管理資源帳戶](manage-resource-accounts.md)] 中的指示進行。 因為 Office 365 不知道內部部署的電話號碼，所以 Contoso 使用 PowerShell 來完成設定。   

- 若要設定雲端自動語音應答，Contoso 按照[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答中所述的步驟進行。 

- 若要設定雲端通話佇列，Contoso 按照[建立雲端通話佇列](create-a-phone-system-call-queue.md)中所述的步驟進行。  


### <a name="sites-with-phone-system-with-calling-plan"></a>使用電話系統進行通話方案的網站

Contoso 必須為商務用 Skype Enterprise Voice 自動語音應答的電話號碼寄回 Office 365 Phone 系統。 這允許將相同的號碼指派為作為自動語音應答使用的服務號碼。 

- 若要移植電話號碼，Contoso 按照將[電話號碼轉接至小組](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)的指示進行，並取得[管理組織電話號碼的](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)其他指導方針。

- 若要設定雲端自動語音應答，Contoso 請按照[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答中所述的步驟進行。

-  若要設定雲端通話佇列，Contoso 按照[建立雲端通話佇列](create-a-phone-system-call-queue.md)中所述的步驟進行。  

 