---
title: Teams Voice Contoso 案例研究
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
description: 多國公司的 Teams 語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121291"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 案例研究：自動電話機和通話佇列

Contoso 熟悉其內部部署商務用 Skype 部署中的自動電話機和通話佇列。 為了瞭解如何設定雲端自動電話機和通話佇列，他們檢閱了 Teams 自動電話機和通話 [佇列的計畫](plan-auto-attendant-call-queue.md)。

## <a name="requirements-depending-on-site-type"></a>根據網站類型的需求

根據網站類型，Contoso 有下列需求：

- 網站類型 A：傳統傳統電話系統 

  網站類型 A 需要保留與接待員相關聯的電話號碼，與自動電話機的號碼相同。 每個網站的重要部門都會擁有自己的通話佇列，以路由給小組成員。 有一種網站混合使用電話系統與直接路由和電話系統與通話方案。  

- 網站類型 B：商務用 Skype 企業語音 

  網站類型 B 有需要遷移到 Teams 的現有自動總機和通話佇列。 Contoso 需要保留與自動總機相關聯的電話號碼。 Contoso 將大部分的網站移至具有通話方案的電話系統。 不過，在少數沒有通話方案的位置，Contoso 將這些網站移至直接路由組。  

- 網站類型 C：商務用 Skype Enterprise Voice &傳統傳統電話系統 

  Site Type C 有現有的自動語音機，這些自動語音機位於傳統的傳統電話系統中。 此網站的決策和組組與網站類型 A 相同。   

- 針對所有網站類型，Contoso 詢問下列問題：

  - 問：我們會使用新號碼或現有號碼嗎？ 
    答：Contoso 決定使用現有電話號碼指派給自動總機的服務帳戶。 

  - 問：何時可以使用自動電話機接聽來電？ 
    答：Contoso 決定設定上班時間，並且將上班時間之後收到的來電重新導向到「工作時間後」自動總機。  

  - 問：如何將通話路由至通話佇列中的成員：話務員、序列或迴圈路由？ 
    答：Contoso 決定使用 Attendant 路由， 

  - 問：我們會如何判斷使用者何時應該或不應該接到來電？ 
    答：Contoso 決定使用通話處理選項來判斷代理人是否可用：目前狀態路由。 


## <a name="configuration"></a>配置

設定自動電話機和通話佇列的步驟包括管理資源帳戶 [中概述的下列步驟](manage-resource-accounts.md)： 

1. 取得服務號碼。 

2. 取得免費的電話系統 - 虛擬使用者授權或付費電話系統授權，以用於資源帳戶或電話系統授權。

3. 建立資源帳戶。 需要自動電話機或通話佇列才能擁有相關聯的資源帳戶。 

4. 將電話系統或電話系統 - 虛擬使用者授權指派給資源帳戶。 詳細資訊，請參閱 [Microsoft 365 Phone System – 虛擬使用者授權](./teams-add-on-licensing/virtual-user.md)。

5. 將服務電話號碼指派給您指派授權的資源帳戶。 

6. 建立電話系統通話佇列或自動通話 

7. 使用通話佇列或自動話務員連結資源帳戶。 


### <a name="sites-with-phone-system-with-direct-routing"></a>使用電話系統直接路由的網站 

Contoso 必須設定當地電信公司提供的電話號碼，做為 Office 365 中的服務號碼。 

- 若要設定透過直接路由提供的電話號碼，Contoso 會遵循管理資源帳戶 [中的指示](manage-resource-accounts.md)。 由於 Office 365 不知道內部部署電話號碼，因此 Contoso 使用 PowerShell 來完成設定。   

- 若要設定雲端自動話務員，Contoso 會遵循設定雲端自動話務員中概述 [的步驟](create-a-phone-system-auto-attendant.md)。 

- 若要設定雲端通話佇列，Contoso 會遵循建立雲端通話佇列中 [概述的步驟](create-a-phone-system-call-queue.md)。  


### <a name="sites-with-phone-system-with-calling-plan"></a>具有電話系統與通話方案的網站

Contoso 必須將商務用 Skype 企業版語音自動語音語音機使用的電話號碼移植到 Office 365 電話系統。 這允許將相同的號碼指派為服務號碼，做為自動總機使用。 

- 若要移轉電話號碼，Contoso 遵循將電話號碼轉接至 [Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 中的指示，並取得管理貴組織 [電話號碼的其他指示](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- 若要設定雲端自動話務員，Contoso 會遵循設定雲端自動話務員中概述 [的步驟](create-a-phone-system-auto-attendant.md)。

-  若要設定雲端通話佇列，Contoso 會遵循建立雲端通話佇列中 [概述的步驟](create-a-phone-system-call-queue.md)。  

