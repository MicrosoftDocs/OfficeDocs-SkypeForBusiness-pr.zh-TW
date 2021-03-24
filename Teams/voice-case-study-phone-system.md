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
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101029"
---
# <a name="contoso-case-study-phone-system"></a>Contoso 案例研究：電話系統

根據地理位置和其他因素，Contoso 的辦公室會使用下列電話解決方案：

- 網站類型 A：商務用 Skype 企業語音

- 網站類型 B：傳統傳統電話系統

- 網站類型 C：商務用 Skype 企業語音與傳統傳統電話系統的組合


若要為整個組織執行 Microsoft Phone System 解決方案，Contoso 必須針對每個網站類型決定下列哪些選項會用於電話系統以連接到公用交換電話網絡 &mdash; &mdash; (PSTN) ：

- 具有通話方案的電話系統 

- 透過直接路由使用自己的 PSTN 電信公司的電話系統 

- 電話系統與通話方案的組合，以及透過直接路由使用自己的 PSTN 電信公司的電話系統組合
 
為了判斷適合其組織的解決方案，Contoso 使用 [Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) 電話解決方案和 Microsoft Teams 中的 Ignite 2019 [會話通話](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)。  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>網站類型 A：商務用 Skype 企業語音 

Contoso 商務用 Skype 企業語音已設定為中樞和語音。 有一個中央位置維護了地區的 PSTN 閘道，為國家/地區的商務用 Skype 企業語音使用者提供 PSTN 的連接。 這些衛星辦公室通常沒有自己的網際網路出口。 這些使用者的數位會位於連接到現有 SBC 的 SIP 主幹上。 

若要判斷已部署的 SBC 是否通過直接路由和媒體旁路的認證，Contoso 檢查了已通過直接路由認證的會話 [框線控制器清單](direct-routing-border-controllers.md)。  

使用者的撥號習慣是使用分機撥打舊版電話系統上的使用者，即使使用者有適用于對等音訊的商務用 Skype 用戶端。 

Contoso 是根據下列問題做出決策：

- 問。 我們需要保留內部部署提供的功能嗎？<br>
  A。 否 

- 問。 我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？<br>
  A。 否 

- 問。 我們需要保留目前的協力廠商電信公司嗎？<br> A。是 (國家/地區) 和否 

- 問。 我們需要部署 SBCs 的ROI 嗎？<br> A。是與否  

- 問。 此地區是否提供 Microsoft PSTN 通話方案？<br> A。是與否 

根據他們問題的答案，Contoso 決定：

- 移動位於 PSTN 通話方案可供電話系統使用之地區的使用者。 

- 將不在提供 PSTN 通話方案的地區的使用者、位於 SBC 上尚未達到ROI 的網站的使用者，以及居住在具有電話法規的國家/地區中的使用者移至具有直接路由的電話系統。 

下圖顯示初始商務用 Skype 企業語音部署，以及此部署如何移遷移到 Microsoft 通話方案與直接路由：

![顯示狀態之前和之後圖表](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>網站類型 B：傳統傳統電話系統

Contoso 有許多運用舊版電話系統的辦公室。 有一部分使用者擁有 E1.64 電話號碼，而其他人則只有分機號碼。 這些號碼會位於 TDM 主幹到 PSTN 閘道。 網站內部撥號是利用分機前方的網站代碼來決定撥號位置所配置的。 使用者的撥號習慣是按分機撥號。   

Contoso 是根據下列問題做出決策：

- 問。 我們需要保留內部部署提供的功能嗎？<br>
  A。 否 

- 問。 我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？<br> A。是的

- 問。 我們需要保留目前的協力廠商電信公司嗎？<br> A。不 

- 問。 我們地區是否提供 Microsoft PSTN 的通話方案？<br> A。是與否 

根據他們問題的答案，Contoso 決定： 

- 移動位於 PSTN 通話方案可供電話系統使用之地區的使用者。 

- 移動不在 PSTN 通話方案可供電話系統直接路由的地區的使用者。 

- 維護與商務關鍵型類比裝置之間的 PSTN 連接。

下列圖表顯示使用遠端網站的原始舊版系統部署，以及使用 Local Media 優化將系統移至直接路由部署：

**原始舊版部署**  
 ![顯示狀態之前和之後圖表](media/voice-case-study-2.png)


**使用直接路由進行部署**

![顯示狀態之前和之後圖表](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>網站類型 C：商務用 Skype 企業語音與傳統舊版電話系統的組合

Contoso 商務用 Skype Enterprise Voice 使用者的數位會位於從電信業者到 SBC 的 SIP 主幹上。 傳統電話系統的數位會位於 PSTN 閘道的 TDM 主幹上。   

Contoso 是根據下列問題做出決策：

- 問。 我們需要保留內部部署提供的功能嗎？<br>
  A。 否 

- 問。 我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？<br> A。不 

- 問。 我們需要保留目前的協力廠商電信公司嗎？<br> A。不 

- 問。 我們需要部署 SBCs 的ROI 嗎？<br> A。是與否  

- 問。 Microsoft 的 PSTN 通話方案是否在此地區提供？<br> A。不 

根據他們問題的答案，Contoso 決定下列專案： 

- 針對將啟用直接路由的舊版電話使用者，Contoso 將 TDM 主幹中的號碼移植到 SBC 的 SIP 主幹，因為 SBC 已通過直接路由認證。 

- 為了支援移往電話系統的使用者子集，並允許繼續透過舊版系統路由，舊版電話系統已設定為 SBC 的下一個躍點。   

- 此外，為了鼓勵使用者行為變更，並移除網站間和內部分機撥號的相依性，Contoso 提供所有內部通話使用 Teams 的指引。  

下圖顯示原始商務用 Skype 企業語音和舊版電話系統部署，以及使用直接路由移入混合式部署：

**原始混合部署** 
 ![顯示狀態前圖表](media/voice-case-study-4.png)

**使用直接路由混合部署** 
 ![顯示狀態前圖表](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>通話方案

若要判斷通話方案的配置需求，Contoso 已審查通話 [方案核心部署決策](calling-plan-landing-page.md#core-deployment-decisions)。 已做出以下決策： 

- 問。 我的使用者是否需要國際通話？<br> A。是的 

- 問。 我的使用者是否都有直接向內 DID 的電話號碼？<br> 答：今天沒有。 啟用的所有使用者都會收到 DID。 

- 問。 我要遮罩或停用本機號碼嗎？<br> A。使用者的本機號碼會遮罩為 Contoso 的當地號碼。 


## <a name="direct-routing"></a>直接路由

Contoso 參與 Ignite，以隨時瞭解 Office 365 功能，包括電話系統和直接路由提供的功能。 技術領導者和架構設計師使用 Ignite 2019 期間所提供的指引來判斷其方向。  使用的關鍵會話： 

- [使用 Microsoft Teams 直接路由規劃成功](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [直接路由的更新](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>配置

### <a name="calling-plans-sites"></a>通話方案網站

若要取得授權並指派電話號碼給使用者，Contoso 遵循設定 [通話方案中的步驟](set-up-calling-plans.md)。 

由於需要指派電話號碼的使用者數目，Contoso 決定使用 PowerShell 來指派電話號碼。 若要瞭解如何使用 PowerShell 來指派數位，除了其他設定之外 &mdash; &mdash; ，Contoso 還使用 [Teams PowerShell 概觀](teams-powershell-overview.md)。  

### <a name="direct-routing-sites"></a>直接路由網站

若要將 Contoso 內部部署電話基礎結構連接到 Microsoft Teams，Contoso 的系統管理員遵循設定直接路由[](direct-routing-configure.md)中的步驟，並查看 Microsoft [Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)中的直接路由影片以尋求指引。  Contoso 也提及認證 SBC 廠商的直接路由部署檔。 

在 SBC 和 Microsoft Phone 系統之間已建立直接路由之後，Contoso 必須測試該組配置。 若要這麼做，Contoso 系統管理員使用 SIP 測試程式用戶端，該用戶端在 [Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)的直接路由更新會話中已討論。 SIP 測試程式用戶端腳本和檔是從 PowerShell 腳本下載，以測試直接路由會話邊界控制器連接。   


### <a name="local-media-optimization"></a>Local Media 優化

Contoso 看到在全球不同區域運用 Local Media 優化的機會。 Contoso 的支援案例在直接路由的 Local [Media 優化中說明](direct-routing-media-optimization.md)。 根據 SBC 廠商和 Microsoft 提供的指導，完成了本地媒體優化的組配置。 Local Media 優化的組組步驟包括： 

- 設定使用者和 SBC 網站 

- 根據 SBC 廠商規格設定 SBC， 

- 新增外部信任的 IP 位址至每個用於 Local Media 優化的網站    

- 定義網路拓撲 

- 定義虛擬網路拓撲 

- 決定模式：一直忽略或僅適用于當地使用者 

## <a name="networking-considerations"></a>網路考慮

Contoso 有一些使用者在啟用電話系統之後，需要長時間遠端工作。 使用者使用 VPN 存取特定的商務用應用程式。 使用 VPN 時，電話系統使用者遇到通話品質降低的問題。 

若要解決品質問題，Contoso 已實施 VPN 分割管道，允許其 Office 365 流量在內部 App 的連接維持在 VPN 上時，可以橫穿網際網路。 若要執行 VPN 分割管道，Contoso 遵循為 [Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel)執行 VPN 分割管道中的指引。  

