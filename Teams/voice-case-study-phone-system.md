---
title: Contoso 案例研究：適用于多國公司電話系統
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
description: Teams多國公司語音案例研究：電話系統
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95ba8e36948a3d61a2e81f9c1954919709eb3a77
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823664"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Contoso 案例研究：適用于多國公司電話系統

根據地理位置和其他因素而定，Contoso 辦公室會使用下列電話語音解決方案：

- 網站類型 A：商務用 Skype 企業語音

- 網站類型 B：傳統的電話語音系統

- 網站類型 C：商務用 Skype 企業語音 與傳統電話語音系統的組合


若要實作整個組織的Microsoft 電話系統解決方案，Contoso 必須針對每個網站類型 &mdash; 判斷 &mdash; 下列哪些選項將與電話系統搭配使用，以連線到公用交換電話網路 (PSTN) ：

- 電話系統通話方案 

- 透過直接路由電話系統與自己的 PSTN 電信業者 

- 電話系統與通話方案的組合，以及透過直接路由與自己的 PSTN 電信業者電話系統
 
為了決定其組織的正確解決方案，Contoso 使用[規劃您的Teams語音解決方案](/microsoftteams/cloud-voice-landing-page)，以及[在 Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-for-calling-in-microsoft-teams-ignite-2019-edition/ba-p/974935)中使用 Ignite 2019 會話通話。  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>網站類型 A：商務用 Skype 企業語音 

Contoso 商務用 Skype 企業語音設為中心並說話。 在區域中，有一個中央位置維護 PSTN 閘道，為國家/地區的商務用 Skype 企業語音使用者提供 PSTN 連線。 這些衛星辦公室通常沒有自己的網際網路出口。 這些使用者的數位位於連接至現有 SBC 的 SIP 主幹上。 

若要判斷已部署的 SBC 是否通過直接路由和媒體旁路的認證，Contoso 已核取 [通過直接路由認證的會話框線控制器清單](direct-routing-border-controllers.md)。  

使用者的撥號習慣是使用擴充功能在舊版電話語音系統上撥號給使用者，即使使用者有可供對等音訊使用的商務用 Skype用戶端。 

Contoso 會根據下列問題來決定：

- 問。 是否需要保留我們的內部部署所提供的功能？<br>
  A. 否 

- 問。 我們需要與協力廠商 PBX 系統及其他電話語音設備進行交互操作嗎？<br>
  A. 否 

- 問。 是否需要保留我們目前的協力廠商電信業者？<br> A.是 (受規範的國家/地區) 和否 

- 問。 是否需要部署 SB 上的 ROI？<br> A.是和否  

- 問。 這個地區是否提供 Microsoft PSTN 通話方案？<br> A.是和否 

根據他們問題的解答，Contoso 決定：

- 移動位於 PSTN 通話方案可供電話系統通話方案的地區中的使用者。 

- 移動不位於 PSTN 通話方案可用區域的使用者、SBCS 上 ROI 尚未符合之網站的使用者，以及位於具有電話語音法規的國家/地區之使用者，以直接路由電話系統。 

下圖顯示初始商務用 Skype 企業語音部署，以及此部署移轉至 Microsoft 通話方案和直接路由的方式：

![圖表會顯示狀態前後。](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>網站類型 B：傳統的電話語音系統

Contoso 有許多辦公室運用舊版電話語音系統。 有一部分使用者有 E1.64 電話號碼，而其他人則只有分機。 這些數位位於 PSTN 閘道的 TDM 主幹上。 網站內部撥號是利用分機前方的網站代碼來設定，以決定路由電話的路由位置。 使用者的撥號習慣是透過分機撥號。   

Contoso 會根據下列問題來決定：

- 問。 是否需要保留我們的內部部署所提供的功能？<br>
  A. 否 

- 問。 我們需要與協力廠商 PBX 系統及其他電話語音設備進行交互操作嗎？<br> A.是的

- 問。 是否需要保留我們目前的協力廠商電信業者？<br> A.不 

- 問。 Microsoft PSTN 的通話方案是否可在我們地區使用？<br> A.是和否 

根據他們問題的解答，Contoso 決定： 

- 移動位於 PSTN 通話方案可供電話系統通話方案的地區中的使用者。 

- 移動不位於 PSTN 通話方案可供電話系統直接路由的區域中的使用者。 

- 維護與商務關鍵類比裝置的 PSTN 連線。

下圖顯示具有遠端網站的原始舊版系統部署，以及使用本機媒體優化移轉到直接路由部署：

**原始舊版部署**  
 ![圖表會顯示狀態前後的圖表。](media/voice-case-study-2.png)


**使用直接路由部署**

![顯示前後狀態的圖表。](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>網站類型 C：商務用 Skype 企業語音 和傳統電話語音系統的組合

Contoso 商務用 Skype 企業語音使用者的號碼位於從電信業者移至 SBC 的 SIP 主幹上。 傳統電話語音系統的數位位於 PSTN 閘道的 TDM 主幹上。   

Contoso 會根據下列問題來決定：

- 問。 是否需要保留我們的內部部署所提供的功能？<br>
  A. 否 

- 問。 我們需要與協力廠商 PBX 系統及其他電話語音設備進行交互操作嗎？<br> A.不 

- 問。 是否需要保留我們目前的協力廠商電信業者？<br> A.不 

- 問。 是否需要部署 SB 上的 ROI？<br> A.是和否  

- 問。 Microsoft 的 PSTN 通話方案是否可在此地區使用？<br> A.不 

根據他們問題的解答，Contoso 決定下列事項： 

- 對於將啟用直接路由的舊版電話語音使用者，Contoso 會將數位從 TDM 主幹移轉至 SBC 的 SIP 主幹，因為 SBC 已通過直接路由認證。 

- 若要支援移至電話系統的使用者子集，並允許透過舊版系統持續路由，舊版電話語音系統已設定為 SBC 的下一個躍點。   

- 此外，為了鼓勵使用者行為變更，並移除網站內部和內部擴充功能撥號的相依性，Contoso 提供所有內部通話使用Teams的指導方針。  

下圖顯示原始商務用 Skype 企業語音和舊版電話語音系統部署，以及使用直接路由移轉到混合部署：

**原始混合部署** 
 ![顯示之前狀態的圖表 1。](media/voice-case-study-4.png)

**含直接路由的** 
 ![ 混合部署顯示之前狀態的圖表 2。](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>通話方案

為了判斷通話方案的設定需求，Contoso 已檢閱 [通話方案核心部署決策](calling-plan-landing-page.md#core-deployment-decisions)。 做出下列決策： 

- 問。 我的使用者需要國際電話嗎？<br> A.是的 

- 問。 我的每個使用者是否有直接向內的 DID 電話號碼？<br> A. 今天就不對了。 所有啟用的使用者都會收到 DID。 

- 問。 我是否想要遮罩或停用來電者識別碼？<br> A.使用者的來電識別碼會被遮罩為 Contoso 的當地號碼。 


## <a name="direct-routing"></a>直接路由

Contoso 出席 Ignite，以持續瞭解Office 365功能，包括可與電話系統和直接路由搭配使用的功能。 技術領導和架構人員使用 Ignite 2019 期間提供的指導方針來判斷其方向。  之前使用的重要會話： 

- [使用Microsoft Teams直接路由規劃成功](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)

- [直接路由的更新](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)


## <a name="configuration"></a>設定

### <a name="calling-plans-sites"></a>通話方案網站

若要取得授權並將電話號碼指派給使用者，Contoso 會依照設定 [通話方案](set-up-calling-plans.md)中的步驟進行。 

由於需要指派電話號碼的使用者數目，Contoso 決定使用 PowerShell 來指派電話號碼。 若要瞭解如何使用 PowerShell &mdash; 指派數位，以及其他設定 &mdash; ，Contoso 也使用[Teams PowerShell 概觀。](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>直接路由網站

若要將 Contoso 的內部部署電話語音基礎結構連線至Microsoft Teams，Contoso 的系統管理員依照設定[直接路由](direct-routing-configure.md)中的步驟進行，並檢閱[Microsoft Teams 中的視訊直接路由以](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)取得指引。  Contoso 也提到通過認證 SBC 廠商的直接路由部署檔。 

在 SBC 和 Microsoft 電話 System 之間設定直接路由之後，Contoso 就必須測試設定。 為了這麼做，Contoso 系統管理員使用了 SIP 測試人員用戶端，該用戶端在[Ignite 2019 的「直接路由更新」會話](https://techcommunity.microsoft.com/t5/microsoft-teams-events-blog/ignite-live-blog-session-vce20-updates-for-direct-routing/ba-p/1025138)中討論過。 SIP 測試人員用戶端腳本和檔是從 PowerShell 腳本下載，以測試直接路由會話框線控制器連線。   


### <a name="local-media-optimization"></a>本機媒體優化

Contoso 發現在全球不同地區運用本機媒體優化的機會。 Contoso 支援的案例請參閱直接 [路由的本機媒體優化](direct-routing-media-optimization.md)。 本機媒體優化的設定是依照 SBC 廠商和 Microsoft 的指引來完成。 本機媒體優化的組態步驟包括： 

- 設定使用者和 SBC 網站 

- 根據 SBC 廠商規格設定 SBC， 

- 將外部信任的 IP 位址新增至用於本機媒體優化的每個網站    

- 定義網路拓撲 

- 定義虛擬網路拓撲 

- 決定模式：永遠略過或只適用于本機使用者 

## <a name="networking-considerations"></a>網路考慮

Contoso 有一些使用者在啟用電話系統之後，需要長時間遠端工作。 使用者使用 VPN 存取特定的商務營運應用程式。 使用 VPN 時，電話系統使用者的通話品質會降低。 

為了解決品質問題，Contoso 已實作 VPN 分割網道，允許其Office 365流量在 VPN 上保留與內部應用程式的連線時周轉網際網路。 若要實作 VPN 分割通道，Contoso 會遵循[針對Office 365實作 VPN 分割網Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel)中的指導方針。  

