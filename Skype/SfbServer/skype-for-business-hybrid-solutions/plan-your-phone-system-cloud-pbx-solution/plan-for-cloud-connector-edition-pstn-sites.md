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
description: 請閱讀本主題，瞭解如何規劃雲端連接器版本 PSTN 網站，以確保高效且經濟高效的呼叫路由。
ms.openlocfilehash: 5f20a5cf7a3395d4695a0e38d21e595982dc6398
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812501"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>規劃 Cloud Connector Edition PSTN 網站
 
請閱讀本主題，瞭解如何規劃雲端連接器版本 PSTN 網站，以確保高效且經濟高效的呼叫路由。
  
本主題描述您需要瞭解的雲端連接器版本及呼叫路由，讓您可以規劃雲端連接器 PSTN 網站。 PSTN 網站是雲端連接器裝置的組合，可在相同的位置部署，以及與其連接的常見 PSTN 閘道。 本主題重點說明如何設定您的雲端連接器網站拓朴，以確保您的雲端連接器網站能以最經濟高效且有效的方式來處理指派給網站的所有使用者的輸入和輸出路由。 如需雲端連接器的詳細資訊和 PSTN 網站的優點，請務必閱讀[商務用 Skype 雲端連接器版本的規劃](plan-skype-for-business-cloud-connector-edition.md)。 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>雲端連接器 PSTN 網站和通話路由

雲端連接器 PSTN 網站是建立拓撲結構，可避免不必要的長途與全國間 tariffs，以及確保輸出緊急呼叫路由至適當的幹線。 為了確保經濟高效且高效地路由通話，包括呼叫緊急服務，您必須仔細規劃 PSTN 網站，以及如何將使用者指派給每一個網站。 
  
在您規劃雲端連接器的過程中，請務必與您的運營商通話，瞭解辦公室和使用者的位置，以及 PSTN trunks 從載波終止的位置。 您必須使用您的運營商來判斷緊急通話的傳送方式，然後使用該資訊來定義雲端連接器 PSTN 網站，並將使用者指派給適當的網站。 例如，您應該確保將 PSTN 網站延伸的資料中心終止的 trunks 設定為處理指派給該網站使用者的所有號碼的輸入和輸出路由。 
  
每個雲端連接器裝置都可以連線到幾個 IP 閘道、IP Pbx 或會話邊界控制器（SBCs）。 因為閘道和 Pbx 已連接至電訊 trunks （PRI 或 SIP trunks），所以雲端連接器裝置會以邏輯方式連線到 PSTN trunks，以進行撥入和撥出通話。 透過雲端連接器和內部部署 PSTN 連線，您就能從本機運營商取得主幹及相關聯的電話號碼。 如果您的企業是大型企業，您可能會有一個以上的電信公司，尤其是當您的公司超過一個城市、州或國家/地區時。 因為您的承運人擁有電話號碼，所以電信公司負責處理緊急通話。
  
商務用 Skype Online 會同等地對待網站中的所有雲端連接器裝置，並會以旋轉方式將撥出電話路由至相同網站中的雲端連接器裝置。 網站中的每個雲端連接器都與同一組 PSTN trunks （完全網狀）相交。 因為每個使用者都與一個雲端連接器 PSTN 網站相關聯，所以來自該使用者的任何出站呼叫（正常或緊急）都將指派給使用者所關聯的 PSTN 網站中的其中一個雲端連接器裝置。 
  
雲端連接器會將靜態呼叫路由至其連接的 IP 閘道、IP-Pbx、SBCs 或直接 PSTN trunks。 雲端連接器還不能根據目的地（最小成本路由）或根據原產地（靜態或動態緊急通話）來動態路由到主幹。 輸入通話不是問題，因為呼叫只能來自與號碼相關聯的幹線。 不過，呼出通話可以移至網站中的任何雲端連接器裝置（以及延伸連接至該雲端連接器裝置的 PSTN trunks），這可能會導致不需要的長途電話。 此外，如果雲端連接器 PSTN 網站是透過不同的區功能變數代碼或運營公司延伸跨資料中心，緊急通話就不會繼續進行。
  
## <a name="an-example"></a>範例

下列範例說明如何將 trunks 群組至 PSTN 網站，以及如何將使用者指派給網站。 若是 Contoso 公司，請假設下列事項：
  
- 有四個使用者： 
    
  - 雷德蒙 WA （美國）中的使用者 A
    
  - Bellevue WA 中的使用者 B （美國）
    
  - Centralia WA 中的使用者 C （美國）
    
  - 前或（美國）的使用者 D
    
- 電信公司 A 在下列情況中提供電話號碼與 trunks：
    
  - 雷德蒙（區域碼425）
    
  - Bellevue （區功能變數代碼425）
    
  - Centralia （區功能變數代碼360）
    
- 電信公司 B 在下列專案中提供電話號碼與 trunks：
    
  -  上海（區功能變數代碼503）
    
因為使用者 A 在雷蒙德（資料中心 A）和 Bellevue 中的使用者 B （資料中心 B）彼此相鄰，且在相同的區號（425）中，因此，電信公司 A 應該能夠在 Bellevue 中的主幹上的使用者 A 進行緊急通話。 
  
因此，使用者 A 和 B 以及 Bellevue 和雷德蒙的雲端連接器 trunks 可能位於同一個雲端連接器 PSTN 網站，如下圖中所示。 一個辦公室中的使用者緊急通話可以傳送至另一個辦公室中的 trunks。 不過，您應該與您的運營商確認這將會運作。
  
![如何設定 PSTN 網站](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
您也可以考慮下列範例：
  
- Centralia 中的使用者 C （由電信公司 A 提供）是兩個小時的磁片磁碟機，並在不同的區號（360）中，與其他運營商在 Bellevue 和雷德蒙425區功能變數代碼中的使用者。 
    
    因此，即使來電是來自載波 A，在 Centralia 區號360中，電信公司的呼叫路由軟體可能會拒絕來自 Bellevue 區域程式碼425中的使用者 B 的傳入緊急通話。 在這種情況下，載體確認雲端連接器及其在 Centralia PSTN 網站中的關聯 trunks 可以跨距離和區功能變數代碼處理通話。
    
- 中的使用者 D 使用由載體 B 提供的數位和主幹，因此，不太可能是由載體 B 所擁有的電話號碼撥打緊急電話。因此，trunks 中的使用者 D 和雲端連接器裝置和相關聯的將必須位於不同的 PSTN 網站中。
    

