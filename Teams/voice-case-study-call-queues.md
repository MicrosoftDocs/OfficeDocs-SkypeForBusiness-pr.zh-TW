---
title: Teams 語音 Contoso 案例研究：自動語音應答和通話佇列
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
description: 適用于多國公司 Teams 語音案例研究：自動語音應答和通話佇列
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50d1ee2d384b200aeab6eefd6ca2de623015b6f2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615839"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Contoso 案例研究：自動語音應答和通話佇列

Contoso 熟悉內部部署商務用 Skype自動語音應答和通話佇列。 若要瞭解如何設定雲端自動語音應答和通話佇列，他們已檢閱 [規劃 Teams 自動語音應答和通話佇列](plan-auto-attendant-call-queue.md)。

## <a name="requirements-depending-on-site-type"></a>需求視網站類型而定

根據網站類型而定，Contoso 有下列需求：

- 網站類型 A：傳統的電話語音系統 

  網站類型 A 需要保留與其自動語音應答號碼建立與接收機相關聯的電話號碼。 這些網站的重要部門會有自己的通話佇列，並路由至小組成員。 混合使用電話系統搭配直接路由和電話系統搭配通話方案的網站。  

- 網站類型 B：商務用 Skype 企業語音 

  網站類型 B 有需要移轉到 Teams 的現有自動語音應答和通話佇列。 Contoso 需要保留與自動語音應答相關聯的電話號碼。 Contoso 將這些網站的大多數移至電話系統與通話方案。 不過，在通話方案無法使用的少數幾個位置，Contoso 會將這些網站移至直接路由設定。  

- 網站類型 C：商務用 Skype 企業語音 &傳統的電話語音系統 

  網站類型 C 有現有的自動語音應答，位於傳統電話語音系統中。 此網站的決策和設定與網站類型 A 相同。   

- 針對所有網站類型，Contoso 會詢問下列問題：

  - 問：我們會使用新的或現有的數位嗎？ 
    答：Contoso 決定使用現有電話號碼指派給自動語音應答的服務帳戶。 

  - 問：自動語音應答何時可以接聽來電？ 
    答：Contoso 決定設定上班時間，並將上班時間之後接聽的電話重新導向至「下班後」自動語音應答。  

  - 問：通話會如何路由至通話佇列中的成員：語音應答、串列或圓圈路由？ 
    答：Contoso 決定使用 Attendant 路由， 

  - 問：我們將如何判斷使用者何時應該接到電話或不應該接聽電話？ 
    答：Contoso 決定使用通話處理選項來判斷專員是否在線上：目前狀態路由。 

## <a name="configuration"></a>設定

設定自動語音應答和通話佇列的步驟包括管理[資源帳戶](manage-resource-accounts.md)中所述的下列步驟：

1. 取得服務編號。

2. 取得免費 **Microsoft Teams 電話資源帳戶** 授權或付費電話系統授權，以搭配資源帳戶或電話系統授權使用。

3. 建立資源帳戶。 若要有相關聯的資源帳戶，必須有自動語音應答或通話佇列。

4. 指派 **Teams 電話標準方案** 或 **Microsoft Teams 電話資源帳戶** 授權給資源帳戶。 如需詳細資訊，請[參閱Microsoft Teams 電話資源帳戶授權。](./teams-add-on-licensing/virtual-user.md)

5. 將服務電話號碼指派給您指派授權的資源帳戶。

6. 建立電話系統通話佇列或自動語音應答。

7. 將資源帳戶連結至通話佇列或自動語音應答。

### <a name="sites-with-phone-system-with-direct-routing"></a>具有直接路由的電話系統網站

Contoso 必須將當地電信業者提供的電話號碼設定為 Office 365 中的服務號碼。

- 若要設定可透過直接路由取得的電話號碼，Contoso 會依照管理 [資源帳戶](manage-resource-accounts.md)中的指示操作。 由於Office 365並不知道內部部署電話號碼，因此 Contoso 使用 PowerShell 來完成設定。   

- 若要設定雲端自動語音應答，Contoso 會遵循設定[雲端自動語音應答](create-a-phone-system-auto-attendant.md)中所述的步驟。 

- 若要設定雲端通話佇列，Contoso 會依照建立雲端 [通話佇列](create-a-phone-system-call-queue.md)中所述的步驟進行。  


### <a name="sites-with-phone-system-with-calling-plan"></a>具有通話方案之電話系統的網站

Contoso 必須將商務用 Skype 企業語音自動語音應答所用的電話號碼移轉至Office 365 電話系統。 這允許將相同的號碼指派為服務號碼，以做為自動語音應答使用。 

- 若要移轉電話號碼，Contoso 會依照將 [電話號碼移轉到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 中的指示進行，並在 [管理貴組織的電話號碼](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)中取得其他指導方針。

- 若要設定雲端自動語音應答，Contoso 會遵循設定[雲端自動語音應答](create-a-phone-system-auto-attendant.md)中所述的步驟。

-  若要設定雲端通話佇列，Contoso 會依照建立雲端 [通話佇列](create-a-phone-system-call-queue.md)中所述的步驟進行。  

