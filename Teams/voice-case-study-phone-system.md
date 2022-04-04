---
title: Contoso 案例研究：電話系統多國公司
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
description: Teams多國公司的語音案例研究：電話系統
appliesto:
- Microsoft Teams
ms.openlocfilehash: abc7c2b3eb8cbbaf98842638526514171a8b23c7
ms.sourcegitcommit: a77116a0b0fd7e3cf14de694c559338bea198851
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2022
ms.locfileid: "64628327"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Contoso 案例研究：電話系統多國公司

根據地理位置和其他因素，Contoso 的辦公室會使用下列電話解決方案：

- 網站類型 A：商務用 Skype 企業語音

- 網站類型 B：傳統傳統電話系統

- 網站類型 C：傳統商務用 Skype 企業語音傳統電話系統的組合


若要為整個組織Microsoft 電話的 Microsoft 電話 System 解決方案，Contoso &mdash; &mdash; 必須針對每個網站類型決定下列選項會與 電話系統 一起使用，以連接到公用交換式電話網絡 (PSTN) ：

- 電話系統通話方案 

- 電話系統直接路由使用自己的 PSTN 電信公司 

- 透過直接路由電話系統電話方案與電話系統 PSTN 電信公司之間的通話組合
 
為了判斷適合其組織的解決方案，Contoso 在 Teams 中[](/microsoftteams/cloud-voice-landing-page)使用規劃您的語音解決方案和 Ignite 2019[會話Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)。  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>網站類型 A：商務用 Skype 企業語音 

Contoso 商務用 Skype 企業語音設定為樞紐和分支。 有一個中央位置維護了地區的 PSTN 閘道，為國家/地區的使用者商務用 Skype 企業語音 PSTN。 這些衛星辦公室通常沒有自己的網際網路出口。 這些使用者的數位會位於連接到現有 SBC 的 SIP 主幹上。 

若要判斷已部署的 SBC 是否通過直接路由和媒體旁路的認證，Contoso 已檢查通過直接路由認證的會話 [框線控制器清單](direct-routing-border-controllers.md)。  

使用者的撥號習慣是使用分機撥打舊版電話系統上的使用者，即使使用者有 商務用 Skype 用戶端可供對等音訊使用。 

Contoso 是根據下列問題做出決策：

- 問。 我們需要保留內部部署提供的功能嗎？<br>
  A. 否 

- 問。 我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？<br>
  A. 否 

- 問。 我們需要保留目前的協力廠商電信公司嗎？<br> A.是 (國家/地區) 和否 

- 問。 我們需要部署 SBCs 的ROI 嗎？<br> A.是與否  

- 問。 此地區是否提供 Microsoft PSTN 通話方案？<br> A.是與否 

根據他們問題的答案，Contoso 決定：

- 移動位於 PSTN 通話方案可用區域的使用者，電話系統通話方案。 

- 移動不在提供 PSTN 通話方案區域的使用者、位於 SBC 上尚未達到ROI 的網站的使用者，以及居住在具有電話法規的國家/地區中的使用者，以直接路由電話系統。 

下圖顯示部署商務用 Skype 企業語音部署，以及此部署如何移移至 Microsoft 通話方案與直接路由：

![圖表會顯示狀態之前和之後。](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>網站類型 B：傳統傳統電話系統

Contoso 有許多運用舊版電話系統的辦公室。 有一部分使用者擁有 E1.64 電話號碼，而其他人則只有分機號碼。 這些號碼會位於 TDM 主幹到 PSTN 閘道。 網站內部撥號是利用分機前方的網站代碼來決定撥號位置所配置的。 使用者的撥號習慣是按分機撥號。   

Contoso 是根據下列問題做出決策：

- 問。 我們需要保留內部部署提供的功能嗎？<br>
  A. 否 

- 問。 我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？<br> A.是的

- 問。 我們需要保留目前的協力廠商電信公司嗎？<br> A.不 

- 問。 我們地區是否提供 Microsoft PSTN 的通話方案？<br> A.是與否 

根據他們問題的答案，Contoso 決定： 

- 移動位於 PSTN 通話方案可用區域的使用者，電話系統通話方案。 

- 移動不在 PSTN 通話方案可用區域的使用者，電話系統直接路由。 

- 維護與商務關鍵型類比裝置之間的 PSTN 連接。

下列圖表顯示使用遠端網站的原始舊版系統部署，以及使用 Local Media 優化將系統移至直接路由部署：

**原始舊版部署**  
 ![圖表會顯示狀態之前和之後。](media/voice-case-study-2.png)


**使用直接路由進行部署**

![顯示狀態之前和之後之狀態圖表。](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>網站類型 C：商務用 Skype 企業語音傳統電話系統的組合

Contoso 商務用 Skype 企業語音使用者的號碼會位於從電信電信企業到 SBC 的 SIP 主幹上。 傳統電話系統的數位會位於 PSTN 閘道的 TDM 主幹上。   

Contoso 是根據下列問題做出決策：

- 問。 我們需要保留內部部署提供的功能嗎？<br>
  A. 否 

- 問。 我們需要與協力廠商 PBX 系統和其他電話設備進行交互操作嗎？<br> A.不 

- 問。 我們需要保留目前的協力廠商電信公司嗎？<br> A.不 

- 問。 我們需要部署 SBCs 的ROI 嗎？<br> A.是與否  

- 問。 Microsoft 的 PSTN 通話方案是否在此地區提供？<br> A.不 

根據他們問題的答案，Contoso 決定下列專案： 

- 針對將啟用直接路由的舊版電話使用者，Contoso 將 TDM 主幹中的號碼移植到 SBC 的 SIP 主幹，因為 SBC 已通過直接路由認證。 

- 為了支援一部分使用者移往舊電話系統並允許繼續透過舊版系統路由，舊版電話系統已設定為 SBC 的下一個躍點。   

- 此外，為了鼓勵使用者行為變更，並移除對網站間和內部分機撥號的相依性，Contoso 提供所有內部電話Teams使用指南。  

下圖顯示原始電話商務用 Skype 企業語音和舊版電話系統部署，以及使用直接路由移入混合式部署：

**原始混合部署** 
 ![顯示前狀態之圖表 1。](media/voice-case-study-4.png)

**使用直接路由混合部署** 
 ![顯示前狀態之圖表 2。](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>通話方案

若要判斷通話方案的配置需求，Contoso 已審查通話 [方案核心部署決策](calling-plan-landing-page.md#core-deployment-decisions)。 已做出以下決策： 

- 問。 我的使用者是否需要國際電話？<br> A.是的 

- 問。 我的使用者是否都有直接向內 DID 的電話號碼？<br> 答：今天沒有。 啟用的所有使用者都會收到 DID。 

- 問。 我要遮罩或停用本機號碼嗎？<br> A.使用者的本機號碼將會遮罩到 Contoso 的當地號碼。 


## <a name="direct-routing"></a>直接路由

Contoso 參與 Ignite，Office 365系統與直接路由電話功能。 技術領導和架構人員使用 Ignite 2019 期間所提供的指引來判斷其方向。  使用的關鍵會話： 

- [使用直接路由規劃Microsoft Teams成功](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [直接路由的更新](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>設定

### <a name="calling-plans-sites"></a>通話方案網站

若要取得授權並指派電話號碼給使用者，Contoso 按照設定通話方案 [中的步驟進行](set-up-calling-plans.md)。 

由於需要指派電話號碼的使用者數目，Contoso 決定使用 PowerShell 來指派電話號碼。 若要瞭解如何使用 PowerShellin &mdash; &mdash; 來指派數位，除了其他設定之外，Contoso Teams [PowerShell 概觀](teams-powershell-overview.md)。  

### <a name="direct-routing-sites"></a>直接路由網站

[若要](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)將 Contoso 內部部署電話基礎結構連接到 Microsoft Teams，Contoso 的系統管理員遵循設定直接路由中的步驟，並查看 Microsoft Teams 中的影片[](direct-routing-configure.md)直接路由以尋求指引。  Contoso 也提及認證 SBC 廠商的直接路由部署檔。 

一旦在 SBC 和 Microsoft 電話 系統之間進行直接路由，Contoso 必須測試該配置。 若要這麼做，Contoso 系統管理員使用 SIP 測試程式用戶端，該用戶端在 [Ignite 2019 的直接路由更新會話中已討論](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)。 SIP 測試程式用戶端腳本和檔是從 PowerShell 腳本下載，以測試直接路由會話邊界控制器連接。   


### <a name="local-media-optimization"></a>Local Media 優化

Contoso 看到在全球不同區域運用 Local Media 優化的機會。 Contoso 的支援案例在直接路由的 Local [Media 優化中說明](direct-routing-media-optimization.md)。 根據 SBC 廠商和 Microsoft 提供的指導，完成了本地媒體優化的組配置。 Local Media 優化的組組步驟包括： 

- 設定使用者和 SBC 網站 

- 根據 SBC 廠商規格設定 SBC， 

- 新增外部信任的 IP 位址至每個用於 Local Media 優化的網站    

- 定義網路拓撲 

- 定義虛擬網路拓撲 

- 決定模式：一直忽略或僅適用于本地使用者 

## <a name="networking-considerations"></a>網路考慮

Contoso 有一些使用者需要長時間遠端工作，才能使用 電話系統。 使用者使用 VPN 存取特定的商務用應用程式。 使用 VPN 時，電話系統通話品質降低。 

若要解決品質問題，Contoso 已套用 VPN 分割管道，允許其Office 365流量在內部 App 的連接維持在 VPN 上時Office 365網際網路。 若要執行 VPN 分割傳輸，Contoso 遵循了針對虛擬使用者套用[VPN 分割Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel)。  

