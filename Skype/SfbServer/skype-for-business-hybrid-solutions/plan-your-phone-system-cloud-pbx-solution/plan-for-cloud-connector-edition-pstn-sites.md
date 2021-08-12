---
title: 規劃 Cloud Connector Edition PSTN 網站
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: 閱讀此主題以瞭解如何規劃雲端連接器 Edition PSTN 網站，以確保有效且經濟划算的呼叫路由。
ms.openlocfilehash: 51bc6c0b7bf536849ebc9d6b1338faa6db8800fee86c4515db4c5f15bf9115b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339959"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>規劃 Cloud Connector Edition PSTN 網站

> [!Important]
> 雲端連接器 Edition 會在2021年7月31日和商務用 Skype 線上時終止。 當您的組織升級至 Teams 後，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話網絡連線至 Teams。
 
閱讀此主題以瞭解如何規劃雲端連接器 Edition PSTN 網站，以確保有效且經濟划算的呼叫路由。
  
本主題說明您需要瞭解的雲端連接器版本和通話路由，以便您可以規劃雲端連接器 PSTN 網站。 PSTN 網站是雲端連接器裝置的組合，部署于相同位置，並與通用 PSTN 閘道相連。 本主題著重于如何設定您的雲端連接器網站拓撲，以確保您的雲端連接器網站可以以最具成本效益且有效的方式，處理所有指派給網站的使用者的輸入和輸出路由。 如需雲端連接器及 PSTN 網站優點的詳細資訊，請務必閱讀商務用 Skype Cloud Connector Edition 的[計畫](plan-skype-for-business-cloud-connector-edition.md)。 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>雲端連接器 PSTN 網站與通話路由

雲端連接器 PSTN 網站是建立的拓撲結構構造，以避免不必要的長途和全國間 tariffs，以及確保輸出緊急通話路由傳送至適當的主幹。 為了確保通話成本效益和有效地路由傳送（包括電話緊急服務），您必須仔細規劃 PSTN 網站，以及如何將使用者指派給每個網站。 
  
在您規劃雲端連接器時，請務必與您的電信公司交談，以瞭解您的辦事處和使用者的位置，以及 PSTN 主幹從載體終止的位置。 您需要與您的電信公司合作，判斷緊急通話的路由方式，然後使用該資訊來定義雲端連接器 PSTN 網站，並將使用者指派給適當的網站。 例如，您應該確定已設定 PSTN 網站的資料中心終止的主幹，該為所有指派給該網站使用者的號碼，處理輸入和輸出路由。 
  
每個雲端連接器裝置都可以連接至多個 IP 閘道、IP PBXs，或會話邊界控制器 (SBCs) 。 因為閘道和 PBXs 會連接到電訊主幹 (PRI 或 SIP 主幹) ，所以雲端連接器裝置會以邏輯方式連線至 PSTN 主幹，以進行撥入和撥出電話。 透過 Cloud Connector 和內部部署 PSTN 連線，您可以從您當地的載體取得主幹和相關聯的電話號碼。 如果您的公司是大型企業，您可能會有一個以上的電信公司，尤其是當您的公司跨越一個以上的城市、省或 country 時。 因為您的電信公司擁有電話號碼，所以電信公司負責處理緊急通話。
  
商務用 Skype線上在網站中平等對待所有的雲端連接器裝置，並將在同一網站中以旋轉方式將撥出電話路由傳送至雲端連接器裝置。 網站中的每個雲端接頭都會與同一組 PSTN 主幹進行跨線連接 (完全網狀) 。 因為每一位使用者都與雲端連接器 PSTN 網站相關聯，所以來自該使用者的任何撥出電話 (一般或緊急) 都會指派給使用者關聯之 PSTN 網站中的其中一個雲端連接器裝置。 
  
雲端連接器會以靜態呼叫路由傳送至其連接的 IP 閘道、IP PBXs、SBCs 或 direct PSTN 主幹。 雲端連接器尚未能夠根據目的地 (，針對最低成本路由) 或根據原產地 (靜態或動態緊急通話) ，以動態路由傳送至主幹。 輸入呼叫不是問題，因為通話只會來自與號碼相關聯的主幹。 不過，撥出電話可以移至網站中的任何雲端連接器裝置 (，也可以擴充連接至雲端連接器裝置的 PSTN 主幹，) 這可能會導致不需要的長途通話。 此外，如果在具有不同區號或運營商的資料中心之間延伸雲端連接器 PSTN 網站，緊急通話不會經歷。
  
## <a name="an-example"></a>示例

下列範例顯示如何將主幹群組為 PSTN 網站，以及如何將使用者指派至網站。 若為 Contoso 公司，請假設下列事項：
  
- 有四個使用者： 
    
  - 華盛頓州的使用者 A (美國) 
    
  - Bellevue WA 中的使用者 B (美國) 
    
  - Centralia WA 中的使用者 C (美國) 
    
  - 位於上海或 (USA 的使用者 D) 
    
- 電信公司 A 在下列專案中提供電話號碼和主幹：
    
  - Redmond (區功能變數代碼 425) 
    
  - Bellevue (地區碼 425) 
    
  - Centralia (地區碼 360) 
    
- 電信公司 B 在下列各項中提供電話號碼和主幹：
    
  -  上海 (區域碼 503) 
    
因為 Redmond (資料中心的使用者 A) 和使用者 B 在 Bellevue 中 (資料中心 B) 彼此相鄰，且在相同地區碼 (425) ，所以電信公司 A 應該能夠在 Bellevue 中主幹的使用者 A 進行緊急通話。 
  
因此，使用者 A 和 B，以及 Bellevue 和 Redmond 的雲端連接器主幹可能位於同一個雲端連接器 PSTN 網站，如下圖所示。 一個辦公室中的使用者緊急通話可以路由傳送到另一個辦公室中的主幹。 不過，您應該檢查您的電信公司是否可正常運作。
  
![如何設定 PSTN 網站](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
請同時考慮下列範例：
  
- Centralia 中的使用者 C （由電信公司 A 提供）是兩個小時的磁片磁碟機，在不同的區號中 (360) ，來自其他電信公司 A Bellevue 和 Redmond 425 區功能變數代碼中的使用者。 
    
    因此，即使來電來自載波 A，Centralia 區號360中的電信公司的呼叫路由軟體可能會拒絕來自 Bellevue 區功能變數代碼425中使用者 B 的傳入緊急通話。 在此情況下，電信公司請務必確認 Centralia PSTN 網站中的雲端連接器和其相關聯的主幹可以跨距離和地區碼處理呼叫。
    
- 中的使用者 D 使用由載體 B 所提供的號碼和主幹，因此，載體 B 不太可能會從電信公司 A 所擁有的電話號碼進行緊急通話。因此，使用者 D 和主幹中的雲端連接器裝置和關聯的必須位於不同的 PSTN 網站。
