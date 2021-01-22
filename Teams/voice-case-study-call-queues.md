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
description: 適用于多國公司的 Teams 語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918729"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 案例研究：自動撥打和通話佇列

Contoso 已熟悉從內部部署商務用 Skype 部署中的自動撥打和通話佇列。 若要瞭解如何設定雲端自動撥打和通話佇列，他們檢閱了 Teams 自動撥打和 [通話佇列的規劃](plan-auto-attendant-call-queue.md)。

## <a name="requirements-depending-on-site-type"></a>依網站類型顯示的需求

根據網站類型，Contoso 的需求如下：

- 網站類型 A：傳統舊版電話系統 

  需要網站類型 A，以保留與總機相關聯的電話號碼與其自動接聽電話的號碼。 每個網站的重要部門都會有自己的通話佇列，以路由給小組成員。 有一個網站混合使用電話系統與直接路由和電話系統以及通話方案。  

- 網站類型 B：商務用 Skype 企業語音 

  網站類型 B 有現有的自動 Attendant 和通話佇列，需要將其遷移到 Teams。 Contoso 需要保留與自動 Attendant 相關聯的電話號碼。 Contoso 將大部分的網站移至有通話方案的電話系統。 不過，在通話方案無法提供的少數幾個位置，Contoso 將這些網站移至直接路由組案。  

- 網站類型 C：商務用 Skype 企業語音&傳統電話系統 

  網站類型 C 的現有自動語音語音人員，是位於傳統的舊版電話系統。 此網站的決策和組組與網站類型 A 相同。   

- 針對所有網站類型，Contoso 詢問下列問題：

  - 問：我們會使用新號碼或現有號碼嗎？ 
    答：Contoso 決定使用現有電話號碼指派給自動 Attendant 的服務帳戶。 

  - 問：系統何時可以使用自動撥打接聽來電？ 
    答：Contoso 決定設定上班時間，將上班時間之後接到的電話重新導向到「上班時間」自動接聽。  

  - 問：如何將通話路由至通話佇列的成員：Attendant、循序或圓形路由？ 
    答：Contoso 決定使用 Attendant 路由， 

  - 問：我們會如何判斷使用者何時應該或不應接到來電？ 
    答：Contoso 決定使用通話處理選項來判斷代理人是否可用：以目前狀態為基礎的路由。 


## <a name="configuration"></a>配置

設定自動參與和通話佇列的步驟包括管理資源帳戶 [中概述的下列步驟](manage-resource-accounts.md)： 

1. 取得服務號碼。 

2. 取得免費的電話系統 - 虛擬使用者授權或付費電話系統授權，以與資源帳戶或電話系統授權一同使用。

3. 建立資源帳戶。 需要自動撥打或通話佇列，才能有相關聯的資源帳戶。 

4. 指派電話系統或電話系統 - 虛擬使用者授權給資源帳戶。 詳細資訊請參閱 Microsoft [365 電話系統 – 虛擬使用者授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)。

5. 將服務電話號碼指派給您指派授權的資源帳戶。 

6. 建立電話系統通話佇列或自動接聽 

7. 將資源帳戶與通話佇列或自動 attendant 連結。 


### <a name="sites-with-phone-system-with-direct-routing"></a>使用電話系統直接路由的網站 

Contoso 必須設定本地電信公司所提供的電話號碼，做為 Office 365 中的服務號碼。 

- 若要設定透過直接路由提供的電話號碼，Contoso 請按照管理資源帳戶 [中的指示進行](manage-resource-accounts.md)。 由於 Office 365 不知道內部部署電話號碼，因此 Contoso 使用 PowerShell 完成設定。   

- 若要設定 Cloud 自動參與，Contoso 按照設定雲端自動 Attendant 中 [概述的步驟進行](create-a-phone-system-auto-attendant.md)。 

- 若要設定雲端通話佇列，Contoso 會遵循建立雲端通話佇列中列出的 [步驟](create-a-phone-system-call-queue.md)。  


### <a name="sites-with-phone-system-with-calling-plan"></a>使用電話系統與通話方案的網站

Contoso 必須針對商務用 Skype 企業語音自動語音語音，將電話號碼埠到 Office 365 電話系統。 這允許將相同的號碼指派為服務號碼，以做為自動 Attendant 使用。 

- 若要移轉電話號碼，Contoso 遵循將電話號碼移轉至 [Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 中的指示，並取得有關管理組織電話號碼 [的其他指引](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。

- 若要設定雲端自動參與，Contoso 按照設定雲端自動 Attendant 中概述 [的步驟進行](create-a-phone-system-auto-attendant.md)。

-  若要設定雲端通話佇列，Contoso 會遵循建立雲端通話佇列中列出的 [步驟](create-a-phone-system-call-queue.md)。  

 