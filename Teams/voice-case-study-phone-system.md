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
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785974"
---
# <a name="contoso-case-study-phone-system"></a>Contoso 案例研究：電話系統

根據地理位置和其他因素，Contoso 擁有使用下列電話解決方案的辦公室：

- 網站類型 A：商務用 Skype Enterprise Voice

- 網站類型 B：傳統舊版電話系統

- 網站類型 C：商務用 Skype 企業語音與傳統舊版電話系統的組合


若要針對其整個組織實施 Microsoft Phone 系統方案，Contoso 必須 &mdash; 針對每個網站類型決定要 &mdash; 與手機系統搭配使用的下列選項，才能連線到公用的交換電話網絡（PSTN）：

- 含有通話方案的電話系統 

- 透過直接佈線提供給自己 PSTN 載體的電話系統 

- 透過直接佈線，搭配電話系統與呼叫方案和電話系統搭配擁有 PSTN 載體
 
若要針對其組織判斷合適的解決方案，Contoso 使用[microsoft 電話解決方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)和[microsoft 團隊中](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)的 Ignite 2019 會話通話。  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>網站類型 A：商務用 Skype Enterprise Voice 

Contoso 商務用 Skype Enterprise Voice 已設定為中心和分支。 這裡有一個中央位置，可在區域中維護 PSTN 閘道，在該區域中提供與商務用 Skype Enterprise Voice 使用者的 PSTN 連線。 這些衛星辦公室通常沒有自己的網際網路出口。 這些使用者的數位駐留在 SIP 主幹上與現有的 SBC 連接。 

為了判斷已部署的 SBC 是否已認證以進行直接路由及媒體旁路，Contoso 已核取已[認證以直接路由的會話框線控制器清單](direct-routing-border-controllers.md)。  

使用者的撥號習慣是使用延伸來撥打舊版電話系統上的使用者，即使使用者有適用于對等音訊的商務用 Skype 用戶端。 

Contoso 根據下列問題進行決策：

- 答疑. 我們需要保留我們內部部署所提供的功能嗎？<br>
  是. 否 

- 答疑. 我們需要與協力廠商 PBX 系統和其他電話裝置進行交互操作嗎？<br>
  是. 否 

- 答疑. 我們需要保留我們目前的協力廠商運營商嗎？<br> 答. 是（管控國家）和 No 

- 答疑. 我們需要取得在 SBCs 上部署的 ROI 嗎？<br> 答. 是和否  

- 答疑. 此地區提供 Microsoft PSTN 通話方案嗎？<br> 答. 是和否 

根據問題的答案，Contoso 決定：

- 移動位於區域中的使用者，該區域中有 PSTN 通話方案可供電話系統使用通話方案。 

- 移動不在可使用 PSTN 通話方案之區域中的使用者、位於 SBCs 中的 ROI 仍需符合的網站，以及駐留在具有直接路線之電話系統的國家/地區中的使用者。 

下圖顯示最初的商務用 Skype 企業語音部署，以及此部署如何遷移到 Microsoft 通話方案和直接路由：

![顯示在狀態之前和之後的圖表](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>網站類型 B：傳統舊版電話系統

Contoso 擁有許多利用舊版電話系統的辦公室。 有一個使用者子集有一個電子1.64 電話號碼，而其他人只有一個副檔名。 這些數位是駐留在 TDM 主幹上的 PSTN 閘道。 站內撥號是利用延伸前的網站程式碼來設定，以決定路由通話的位置。 使用者的撥號習慣是透過副檔名撥號。   

Contoso 根據下列問題進行決策：

- 答疑. 我們需要保留我們內部部署所提供的功能嗎？<br>
  是. 否 

- 答疑. 我們需要與協力廠商 PBX 系統和其他電話裝置進行交互操作嗎？<br> 答. 是

- 答疑. 我們需要保留我們目前的協力廠商運營商嗎？<br> 答. 沒有 

- 答疑. 我們的地區提供 Microsoft PSTN 的通話方案嗎？<br> 答. 是和否 

根據問題的答案，Contoso 決定： 

- 移動位於區域中的使用者，該區域中有 PSTN 通話方案可供電話系統使用通話方案。 

- 將沒有位於 PSTN 通話方案的區域中的使用者移至可直接傳送的電話系統。 

- 維護與業務關鍵型類比裝置的 PSTN 連線。

下列圖表顯示具有遠端網站的原始舊版系統部署，以及使用本機媒體優化進行直接路由部署的遷移：

**原始舊版部署**  
 ![顯示在狀態之前和之後的圖表](media/voice-case-study-2.png)


**使用直接路由進行部署**

![顯示在狀態之前和之後的圖表](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>網站類型 C：商務用 Skype 企業語音與傳統舊版電話系統的組合

Contoso 商務用 Skype Enterprise Voice 使用者的電話號碼是由電信公司在 SIP 主幹中駐留給 SBC。 傳統電話系統的數位駐留在 TDM 幹線上，是 PSTN 閘道。   

Contoso 根據下列問題進行決策：

- 答疑. 我們需要保留我們內部部署所提供的功能嗎？<br>
  是. 否 

- 答疑. 我們需要與協力廠商 PBX 系統和其他電話裝置進行交互操作嗎？<br> 答. 沒有 

- 答疑. 我們需要保留我們目前的協力廠商運營商嗎？<br> 答. 沒有 

- 答疑. 我們需要取得在 SBCs 上部署的 ROI 嗎？<br> 答. 是和否  

- 答疑. 此地區提供 Microsoft 的 PSTN 通話方案嗎？<br> 答. 沒有 

根據問題的答案，Contoso 決定下列事項： 

- 針對將啟用直接路由的舊版電話使用者，Contoso 會將 TDM 主幹中的數位移植到 SBC 的 SIP 幹線，因為 SBC 已認證直接路由。 

- 若要支援移至電話系統的使用者子集，並允許持續路由透過舊版系統，舊版電話系統會設定為 SBC 的下一個躍點。   

- 此外，為了鼓勵使用者行為變更並移除在站內延伸撥號的相依性，Contoso 提供的指導方針將團隊用於所有內部通話。  

下列圖表顯示原始商務用 Skype Enterprise Voice 與舊版電話系統部署，以及使用直接路由進行混合式部署的遷移：

**原始混合式部署** 
 ![在狀態之前顯示的圖表](media/voice-case-study-4.png)

**使用直接路由** 
 ![ 進行混合式部署在狀態之前顯示的圖表](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>通話方案

為了判斷通話方案的設定需求，Contoso 已檢查[通話方案核心部署決定](calling-plan-landing-page.md#core-deployment-decisions)。 產生的決定如下所示： 

- 答疑. 我的使用者需要國際通話嗎？<br> 答. 是 

- 答疑. 我的使用者是否每個都有直接向內撥電話號碼？<br> 答. 並非今天。 所有啟用的使用者都會收到已執行的動作。 

- 答疑. 我想要遮罩或停用本機號碼嗎？<br> 答. 使用者的本機號碼會遮罩為 Contoso 的當地號碼。 


## <a name="direct-routing"></a>直接路由

Contoso 已參與 Ignite，以維持目前的 Office 365 功能，包括可在手機系統和直接路由中使用的功能。 技術領導和架構師使用 Ignite 2019 期間提供的指導方針來決定其方向。  所用的主要會話： 

- [使用 Microsoft 團隊直接路由來規劃成功](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [直接路由的更新](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Configuration

### <a name="calling-plans-sites"></a>通話方案網站

若要取得授權並將電話號碼指派給使用者，Contoso 請按照[設定通話方案](set-up-calling-plans.md)中的步驟進行。 

由於需要指派電話號碼的使用者數目，Contoso 決定要使用 PowerShell 來指派電話號碼。 若要進一步瞭解如何使用 PowerShell 指派數位， &mdash; 除了其他設定 &mdash; Contoso 使用[團隊 PowerShell](teams-powershell-overview.md)外。  

### <a name="direct-routing-sites"></a>直接路由網站

若要將 Contoso 的內部部署電話結構連線至 Microsoft 團隊，Contoso 的系統管理員遵循[設定直接路由](direct-routing-configure.md)及查看[microsoft 團隊中的視頻直接路由中](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)的步驟以取得指導方針。  Contoso 也會參照由認證的 SBC 轉銷商提供的直接路由部署檔。 

在 SBC 與 Microsoft Phone 系統之間設定直接路由之後，Contoso 必須對其進行測試。 若要這樣做，Contoso 系統管理員會使用 SIP 測試者用戶端，在[Ignite 2019 的直接路由會話更新](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)中討論。 SIP 測試者用戶端腳本和檔都是從 PowerShell 腳本下載，以測試直接路由會話框線控制器連線。   


### <a name="local-media-optimization"></a>本機媒體優化

Contoso 在全球不同地區看到了利用本機媒體優化的機會。 Contoso 的支援案例將在[本機媒體優化中說明，以進行直接路由](direct-routing-media-optimization.md)。 以下是由 SBC 供應商和 Microsoft 提供的指導方針完成本機媒體優化的設定。 本機媒體優化的設定步驟包括： 

- 設定使用者和 SBC 網站 

- 根據 SBC 廠商的規格來設定 SBC， 

- 將外部信任的 IP 位址新增到用於本機媒體優化的每個網站    

- 定義網路拓撲 

- 定義虛擬網路拓撲 

- 判斷模式：總是略過或只適用于本機使用者 

## <a name="networking-considerations"></a>網路考慮

Contoso 有許多使用者需要在啟用電話系統之後，在一段時間內進行遠端作業。 使用者使用 VPN 存取特定的商務應用程式。 在 VPN 上，電話系統使用者遇到通話品質下降的情況。 

若要解決品質問題，Contoso 已實現 VPN 分割隧道，允許其 Office 365 通訊在與內部 app 連線之後，在 VPN 上保留。 若要實現 VPN 分割隧道，Contoso 遵循[針對 Office 365 實現 vpn 分割隧道的](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)指導方針。  

 





