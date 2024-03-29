---
title: 規劃 Microsoft Teams 的通話路由流程
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Phone System
description: 瞭解如何在 Microsoft Teams 中規劃自動語音應答和通話佇列的通話路由流程。
ms.openlocfilehash: 876198578bfc0387f00890d393a90ed73bc215c5
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614456"
---
# <a name="plan-your-call-routing-flow"></a>規劃您的通話路由流程

在規劃程式中，建議您在圖表中為組織建立呼叫路由。 圖表可協助決定撥入貴組織之人員最有效率的路由。 您也可以使用圖表來判斷您需要建立的自動語音應答和通話佇列，以及服務號碼、授權和資源帳戶等相關需求。

讓我們看看自動語音應答和通話佇列如何路由通話。

自動語音應答會以下列其中一種方式路由所有通話：

- **立即重新導向** - 電話可以重新導向至其中一個呼叫路由目的地 (列于下方，) 接聽或在初始問候之後立即傳輸。
- **根據撥號選項重新導向** - 您可以導向來選擇指派給其電話鍵臺上號碼的選項，0-9。 每個撥號鍵都可以指派通話路由目的地。
- **依名稱或分機撥號給連絡人** ：可以指示來電者撥打組織目錄中嘗試連絡之人員的分機號碼，或是拼寫該人員的名稱。
- **中斷聯** 機 - 自動語音應答可以掛斷通話。

> [!NOTE]
> 單一自動語音應答只能支援單一「撥號方式」。  若要允許來電者依名稱和號碼撥號，您必須建立自動語音應答，其中包含依名稱撥號的選項，以及另一個用於分機撥號的選項。  每個選項都會路由至針對這些「撥號依據」案例設定的個別自動語音應答。

當自動語音應答或通話佇列重新導向電話時，您可以從下列通話路由目的地中選擇：

- **組織中的** 人員- 組織中可接聽語音通話的人員。 這可以是線上使用者或使用商務用 Skype Server託管在內部部署的使用者。
- **語音應用程式** - 另一個自動語音應答或通話佇列。 選擇與目的地相關聯的資源帳戶。
- **外部電話號碼** - 任何電話號碼。 請參閱 [外部傳輸技術詳細資料](create-a-phone-system-auto-attendant.md?tabs=additional-resources)。

- **語音信箱** - 與您指定的 Microsoft 365 群組相關聯的語音信箱。 您可以選擇是否要語音信箱轉譯，以及「請在鈴聲後面留下訊息」。 系統提示。
- **運** 算符 (自動語音應答僅) - 自動語音應答定義的運算子。 定義運算子是選用的。 運算子可以是此清單中的任何其他目的地。

自動語音應答會針對在上班時間以外和假日接聽的電話，提供個別的來電路由選項。

通話佇列會保留來電者，直到指派到佇列的專員可以接聽來電。 有兩種情況下，來電者可能會被導向佇列外：

- **通話溢位** - 如果佇列中的通話數目超過您設定的限制，則新來電者會重新導向到佇列外。
- **通話逾時** - 如果來電者排入佇列的時間超過設定的逾時設定，則會將來電者重新導向到佇列之外。

從佇列中重新導向的電話可以傳送至上述所列的任何通話路由目的地，但電信業者除外。  (通話佇列沒有電信業者，但您可以將來電者重新導向至您為自動語音應答所設定的電信業者相同的目的地。) 

下列範例顯示使用自動語音應答和通話佇列的通話路由範例。

![使用自動語音應答和通話佇列路由的通話圖表。](media/attendant-and-queue-call-routing.png)

在上述範例中：

- 零 (0) 鍵會將來電者重新導向至電信業者。 該自動語音應答的運算子已設定為 **組織中的** 人員。
- 一 (1) 鍵會將來電者重新導向至銷售通話佇列。 此通話佇列已連線至包含指派給佇列之銷售團隊的團隊。
- 兩個 (2) 鍵會將來電者重新導向到支援通話佇列。 此通話佇列已連線至包含指派給該團隊之支援小組的團隊。
- 支援電話佇列具有透過中間自動語音應答的直接電話號碼。 讓自動語音應答接聽支援線允許個別的下班時間和假日通話路由。
- 三 (3) 鍵會將使用者重新導向至公司目錄的另一個自動語音應答。 公司目錄自動語音應答可讓來電者撥打組織中的個人名稱或分機。

我們建議您建立類似上述圖表的一或多個圖表，以對應您的通話路由。 請務必在圖表或隨附的檔中包含下列專案：

- 哪些自動語音應答會透過電話號碼直接存取？
- 每個自動語音應答的下班時間和假日路由要求為何？
- 每個通話佇列的成員資格。  (您可以個別新增使用者，或將佇列對應到不同類型的群組。 將佇列對應到團隊可提供最多樣化的體驗。) 

以下是一些路由最佳做法的通話：

- 查看您現有的通話系統，並分析來電的類型和頻率。 使用此資訊來協助通知您的自動語音應答和通話佇列結構。
- 在功能表中最早放置最常見的選項，以儘快路由通話。
- 除非 24 月 7 日有可用的佇列，否則請避免將服務號碼直接連線到通話佇列。 通話佇列不允許個別處理下班時間或假日的通話。 如果您想要有包含直接號碼的佇列，請將號碼指派給自動語音應答，自動在上班時間內重新導向至佇列。
- 如果您接到許多來電要求公司的基本資訊，例如上班時間、位置或網站位址，請考慮建立自動語音應答，以錄製的訊息回答這些問題。
- 將功能表項目清單保留為五個或五個以下。 來電者可能無法記住五個以上的選項。 如果需要更多選項才能正確路由通話，請使用巢狀自動語音應答。
- 請先描述服務，後面接著按 (的選項，例如：針對 Sales，請按 1) ，而不是用另一種方式來 (例如。 按 1 以取得銷售) 。
- 您的來電者會瞭解您的使用者術語，而不是您內部可能會使用的內容。
- 避免經常更新來電路由。 如果您未來變更自動語音應答的功能表選項，請在前 30 天的語音提示中叫出該選項。
