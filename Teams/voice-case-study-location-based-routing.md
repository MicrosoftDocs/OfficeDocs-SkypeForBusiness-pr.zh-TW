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
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785968"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso 案例研究：以位置為基礎的路由

位置式路由（LBR）是一項功能，可根據原則與使用者在撥打電話或接聽電話時的物理位置來限制付費略過。  

## <a name="overview"></a>概觀

Contoso 在國家/地區中有兩個辦事處，在這種情況下，不能避開公開的交換電話網絡（PSTN）提供者來減少長途通話成本。 主要辦事處有一個由主要辦公室和第二個辦公室使用的網際網路連線。 每個辦公室都有自己的會話邊界控制器（SBC）連線至 PSTN 運營商。  
 
在此國家/地區，Contoso 已針對其商務用 Skype 部署設定 LBR。 若要決定如何設定團隊的 LBR，請按 Contoso 讀取[方案位置，直接傳送路由](location-based-routing-plan.md)。 Contoso 已決定在撥打電話時，小組和商務用 Skype 會在相同的案例中進行，當您收到來電時，可以將 PSTN 來電轉接給小組使用者，以及您可以將另一個小組使用者轉接至 PSTN 通話。  

在商務用 Skype 中，LBR 是使用會話邊界控制器（SBC） SIP 幹線（連接至 PSTN 載波）進行設定。 針對這個 SBC，Contoso 已檢查[經過驗證的 SBCs 清單](direct-routing-border-controllers.md)，並判斷已部署的 SBC 已認證以直接路由，但尚未針對媒體旁路進行認證。 若要支援 LBR，直接路由必須設定至 SBC 現場，必須是局域網出口，而 SBC 必須針對媒體旁路進行設定。 根據這項資訊，Contoso 決定下列事項：

- 若要推遲團隊 LBR 的啟用，直到現有的 SBC 驗證了媒體旁路。   

- Contoso 決定使用主要網站 SBC 來取得 Office 365 的直接路線。  主網站 SBC 將是遠端網站的 proxy SBC。  

- Contoso 使用以印度為基礎的協力廠商顧問，協助 LBR 設定與國家/地區的電話公司進行認證。  

- 若要支援從辦公室以外的使用者進行 PSTN 通話，提供給員工的公司頒發的行動電話。 

下列圖表顯示符合需要以位置為基礎路由之電話規章之國家/地區的部署之前和之後的情況：

**原始部署**

![在狀態之前顯示的圖表](media/voice-case-study-5.png)

**使用直接路由進行部署**

![在狀態之前顯示的圖表](media/voice-case-study-6.png)


## <a name="configuration"></a>Configuration 

若要設定團隊中的網路元件，Contoso 按照[管理雲端語音功能之網路拓撲](manage-your-network-topology.md)中的指示進行。 Contoso 已完成下列步驟以設定以位置為基礎的路由： 

- 定義網路區域-已定義一個網路區域。 

- 定義網路網站-定義了兩個網路網站。 在區域中的每個辦公室位置都有一個網站。

- 定義網路子網-辦公室位置中的每個樓層都有自己的有線和無線網路子網。 此設定會針對 Contoso 產生20個子網。 

- 定義信任的 IP 位址-SBC 的外部點對點 IP 位址已新增至信任的 IP 位址。  

