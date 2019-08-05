---
title: 規劃服務管理和品質 |技術就緒性
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: 使用本指導方針來瞭解傳送和維護高品質 Microsoft 團隊部署所需的需求。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3bc311fc2099f6162115d1c341d088a49c94da0
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2019
ms.locfileid: "36184194"
---
![升級歷程圖表, 強調技術就緒階段](media/upgrade-banner-tech-readiness.png "升級歷程階段, 重點放在技術準備階段")

本文是您升級歷程的技術就緒階段 (您可以與使用者準備階段並行完成的活動) 的一部分。 繼續之前, 請先確認您已從先前階段完成這些活動:

- [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
- [已瞭解商務用 Skype 與團隊的共存與互通性](https://aka.ms/SkypeToTeams-Coexist)
- [已選擇升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<!-- [!INCLUDE [envision-planning-for-service-management-and-quality-complete-guide](envision-planning-for-service-management-and-quality-complete-guide.md)]-->

# <a name="plan-for-quality"></a>規劃品質

如果您要部署音訊、影片或會議, 您可以採取一些額外步驟來針對該功能優化您的環境。 此內容將提供傳送及維護高品質 Microsoft 團隊部署所需的需求。 您可以規劃服務管理和品質, 在第一次試驗或生產部署之前, 協助確保順利進行部署。

本指南分為下列幾個區段:

- 首先是 underpin 品質的使用者經驗與重要元件的概覽。 這將重點放在向 Microsoft 團隊加入前重點關注的區域。

- 第二, 在第一個使用者試驗或生產部署之前規劃支援模型以管理 Microsoft 團隊的指導方針。 本節描述需要定期執行的工作, 以維持高品質的小組部署。 此外, 本節還會向您介紹您可以用來開始瞭解及 operationalizing 這些任務的進一步指導方針。

- 第三, 特定指導方針可協助規劃貴組織中的網路和端點, 以支援 Microsoft 團隊。

- 最後, 後續步驟會與相關內容的參考匯總。

## <a name="key-technical-components-that-affect-user-experience"></a>影響使用者體驗的重要技術元件

本區段將會討論影響使用者體驗的重要技術元件。 在檢查主要元件之前, 請務必瞭解使用者體驗, 以及它在實現貴組織的業務目標時的重要性。 讓我們來回顧我們如何先定義使用者經驗。

### <a name="user-experience-defined"></a>已定義的使用者體驗

當您部署 Microsoft 團隊時, 以及使用者採用團隊作為核心共同作業及通訊解決方案時, 就能實現商業目標。 品質可協助確保積極的使用者體驗, 這是驅動使用方式與採納的關鍵屬性。 透過提供高品質的服務來 delights 人員、個人和小組, 就能滿懷信心, 並找出使用該服務的新且新穎的方式來促進業務效益。

在這種情況下, 使用者在小組中的經驗是人員的情緒, 並對服務提供看法。 對使用者體驗有何影響？ 其範圍從使用者瞭解如何使用團隊並將其併入其日常工作流程中, 以體驗卓越的通話品質, 且無論身在何處都能可靠地連線。 使用者體驗在本質上非常廣泛;本文只對那些可由您的組織控制的技術元素進行重視。 您可以在[為團隊準備組織](https://aka.ms/SkypeToTeams-UserReadiness)中找到有關使用者準備就緒的其他資訊。

針對提供出色的使用者體驗而言, 部署極為重要的需求, 尤其是在使用團隊中的雲端語音功能時。 將 Microsoft 團隊視為具有其他通訊與共同作業投資的第一類公民是很重要的, 您也可以據此設定即時流量的優先順序。 下節概述影響使用者體驗的關鍵元件。 在其他章節中, 我們將為您提供如何開始規劃以部署及維護構成品質的關鍵元件的指導方針。

### <a name="key-components-of-quality"></a>品質的重要元件

組織或支援合作夥伴應該在小組部署的技術準備階段中開始規劃三個主要元件: 服務管理、網路和端點。 這三個區域的組合都是使用者體驗品質的基礎。

說明![三個品質元件的圖表](media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "說明三個品質元件的圖表, 以及服務管理如何與所有三個元件重迭。")

#### <a name="service-management"></a>服務管理

服務管理可以分為兩種不同的職責類別:

- **Microsoft 責任**。 Microsoft 負責 Office 365 服務所包含的基礎結構元件。 Microsoft 對客戶有責任, 以確保其任何連接至團隊的使用者都提供可靠且優質的體驗。

- **客戶責任**。 您和您的組織負責管理 Office 365 服務、內部部署網路和使用者端點的各個方面。 例如, 當新的 IP 位址新增至 Office 365 時, 您必須更新適當的防火牆, 才能允許與新端點通訊, 避免使用者中斷。

如需服務管理規劃的詳細指導方針, 請參閱[規劃服務管理](#plan-for-service-management)。

#### <a name="network"></a>局域網

在大多陣列織中, 網路最初是設計來提供存取資料中心的資料和應用程式。 以雲端為基礎的應用程式 (例如 Office 365) 需要變更這些網路, 以支援小組所需的新 access 和資料流程程。 您必須先評估並優化您目前的網路, 才能讓貴組織中的小組使用者使用。 在利用雲端語音功能時, 這是極其重要的。

在傳統網路中, 使用者將需要遍歷組織的周邊網路來存取團隊。 許多組織會有安全的裝置, 例如 proxy 伺服器、防火牆及 Vpn, 可以封鎖、妨礙或提供網路流量的未優化路徑。

此外, 核心內部網路需要經過優化, 且大小適當, 才能提供足夠的容量和品質來支援小組工作負載, 包括即時媒體。 您可以使用頻寬規劃、修正及優化, 協助確保您的網路能提供高品質且高效的 Office 365 路徑。

如需網路規劃的詳細指導方針, 請參閱[規劃網路品質](#plan-for-network-quality)。

#### <a name="endpoints"></a>端點

Microsoft 團隊支援各種不同的端點。 從電腦到平板電腦, 您可以隨時隨地從幾乎任何裝置存取團隊。

若要為您的使用者提供最佳的體驗, 您必須考慮下列重要方面: 您的端點是否符合團隊的硬體和軟體需求？ 您是否已設定並優化端點以支援 Wi-fi 網路？ 您會使用哪些裝置撥打及接聽語音通話？ 哪些裝置已針對團隊進行優化？

如需有關端點規劃的詳細指導方針, 請參閱[規劃端點品質](#plan-for-endpoint-quality)。

## <a name="plan-for-service-management"></a>規劃服務管理

服務管理是一個廣泛的主題, 涵蓋在部署並為使用者啟用 Microsoft 團隊服務之後的日常作業。 [團隊服務] 包含 Microsoft Office 365 和部署于內部部署的基礎結構元件 (例如 [網路])。

服務管理的概念很可能不是大多陣列織的新概念。 您可能已經實現與現有服務相關聯的進程和工作。 如此一來, 您可能會在規劃服務管理時補充所需的內容, 以備日後支援 Microsoft 團隊。

服務管理包括管理 Microsoft 團隊端到端的所有活動與程式。 如先前所述, 服務管理的部分元件 (由 Office 365 服務本身所組成的基礎結構元件) 是 Microsoft 的責任, 而客戶對其使用者負責管理團隊的各個方面,網路以及它們所提供的端點。 檔的此章節將重點放在服務管理視點中客戶的責任。

說明![三個品質元件的圖表](media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "說明三個品質元件的圖表, 以及服務管理如何與所有三個元件重迭。重點放在服務管理上。")

### <a name="introduction-to-the-operations-guide"></a>操作指南簡介

**何謂**、**誰**, 以及**如何**在服務管理方面需要解答的三個重要問題。

您可以使用 [[操作指南](1-drive-value-operate-my-service.md)] 協助您解決這三個問題。 本指南提供每日、每週、每月以及視需要執行的活動清單。 這些活動和工作對於維護高品質的小組部署而言是至關重要的。 決定在服務管理中負責執行特定活動的人員, 是規劃中需要儘早進行, 以確保順利進行部署的重要層面[](upgrade-enlist-stakeholders.md) 。 在您發現任務和活動之後, 必須先瞭解這些工作和活動, 然後再按您指派給他們的群組或人員。 本操作指南針對如何執行每項工作以及/或外部內容的參考, 提供相關知識與指導方針。

### <a name="operational-role-mapping"></a>操作角色對應

儘早規劃服務管理是一個重要的里程碑, 因為「操作階段」是在第一個試驗使用者啟用時開始。 專案小組必須審查並同意所需的工作與活動, 找出負責每個作業任務的小組, 然後從各個小組取得承諾並登出。

登出完成後, 負責的小組必須開始 operationalizing 這些角色和職責。 這可能包括訓練與準備、更新人力資源模型, 或確保外部合作夥伴已準備好交付。

當您收集[專案小組](upgrade-enlist-stakeholders.md)時, 對應的操作角色能讓所有團隊在試驗期間開始其運作工作, 並在部署開始之後, 確定一切都已準備好。

本操作指南提供對應至一般角色的一般工作清單, 這些工作應該在大多數情況下都有效。 您必須自訂這些職責, 才能為您的組織作業。

### <a name="the-quality-champion-role"></a>品質擁護者角色

群組或個人需要負責所有組織中的品質。 這是服務管理中最重要的角色。 品質擁護者是指派給人員或群組的客戶角色, 他們會熱情他們的使用者經驗。 這個角色需要技能來識別環境中的趨勢, 以及與其他團隊合作來促進修正的贊助。 品質擁護者的最佳候選方案通常是客戶服務擁有者, 他們可以根據組織的大小與複雜性而定, 誰是熱情使用者體驗的人員或群組。

[品質擁護者] 利用現有的工具與已記錄的程式, 例如 [通話品質儀表板] (CQD) 和 [品質體驗檢查指南], 以監控使用者體驗、識別品質趨勢, 以及在必要時進行磁片磁碟機修正。 品質擁護者與各個小組合作, 以促進修正動作, 向指導委員會報告其進度和開啟的問題。

作業指南中已記錄與角色相關聯的工作和活動。 這個角色應該在[規劃階段](https://aka.ms/SkypeToTeams-Plan)指派。 Operationalizing 品質擁護者角色的主要步驟是取得該角色所需的知識, 並確保準備好要提供該工作所需的預備作業。 此角色的主要工作是執行定期品質體驗審查。

### <a name="introduction-to-the-quality-experience-review-guide"></a>[品質體驗回顧指南] 簡介

[品質體驗檢查指南] 中有一組活動, 可在主要區域中評估並提供修正指導方針, 這些功能會對改善使用者體驗產生最大的影響, 如下圖所示。

說明![在品質體驗檢查期間檢查之區域的圖表]此(media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "圖表說明在品質檢查期間檢查的主要區域。")

透過不斷評估與修正本檔中所述的區域, 您可以減少對使用者經驗造成負面影響的可能性。 在部署中遇到的大多數使用者體驗問題, 都可以分為下列類別:

- 防火牆或 proxy 配置不完整

- 低 wi-fi 覆蓋範圍

- 頻寬不足

- 點對點

- 使用未優化或內建的音訊裝置

- 有問題的子網或網路裝置

[品質體驗回顧指南] 中所提供的指導方針主要是使用 [通話品質儀表板 (CQD)] 作為主要工具來報告和調查所述的每個區域, 並將焦點放在音訊上以最大化採納與影響。 針對網路所做的任何優化, 以改善音訊體驗, 也會直接翻譯成影片和桌面共用的改良功能。

我們強烈建議您提前提名品質擁護者。 命名之後, 他們應該開始熟悉品質體驗回顧指南中的內容。

您可以在[此](https://aka.ms/qerguide)找到品質體驗回顧指南。

## <a name="plan-for-network-quality"></a>規劃網路品質

規劃網路品質將是下一節的重點。

說明![三個品質元件的圖表](media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "說明三個品質元件的圖表, 以及服務管理如何與所有三個元件重迭。焦點放在網路上。")

如先前所述, 在加入 Microsoft 團隊之前規劃網路品質是至關重要的。 如需進一步瞭解網路準備, 請參閱為[Microsoft 團隊準備貴組織的網路](prepare-network.md)。

在大多陣列織中, 網路可包含受管理和非託管的網路。

受管理的網路是組織可直接控制之網路基礎結構的元件。 因此, 受管理的網路會直接影響可提供給即時流量負載的品質。

相反地, 非託管的網路是客戶擁有有限控制權或不控制權的網路區段。

組織與 Office 365 之間的網際網路連線是客戶有限控制的網路。 網路是由 ISP 管理, 但組織應該能夠透過升級頻寬、advocating 路由優化, 或在其他情況下發生故障-切換 Isp 來影響網路品質。

在旅館或咖啡廳中的家用網路或網路是客戶無法控制的網路範例。

在下列各節中, 我們會將重點放在受管理的網路品質需求上。

### <a name="key-network-planning-areas"></a>重要的網路規劃區域

下列各節將重點放在提供高品質網路的重要區域上。

> [!NOTE]
> 許多網路由於升級、擴充或其他業務需求而逐漸隨著時間發展。 請確定您有適當的運作程式, 以維護這些區域做為服務管理規劃的一部分。

#### <a name="bandwidth"></a>量

頻寬規劃是網路就緒活動的一個重要層面。 確保有足夠的頻寬可滿足 Microsoft 團隊工作負載的需求。 若要能夠以適當大小的現有網路為目標, 您必須瞭解目前已調配的專案、目前的利用率, 以及最終的可用頻寬。

若要測量目前的利用率, 您必須監視網路。 此測量值可以用來做為頻寬規劃的起點。 此外, 在部署期間和部署之後, 網路應該會持續受到監視, 以確保網路已足夠提供。

> [!NOTE]
> 監控網路利用率時, 請務必避免在一天中使用平均值。 這些平均值可以包含扭曲結果的非核心時間。 平均值可以隱藏高峰期並掩蓋基本問題。

#### <a name="quality-of-service-qos"></a>服務品質 (QoS)

QoS 應該在受管理的網路的所有區段 (即使是已充分為頻寬提供的網路) 中實現。 在後一種情況下, 當網路負載不應發生時, QoS 就會成為風險降低的行為。 當您實現 QoS 時, 語音流量將會成為優先順序, 因此這些意外事件不會影響品質。

QoS 實現應該包括網路領域, 從端點一直到出口點, 然後從出口點回到終點。 這可確保語音交通會依兩個方向的優先順序進行劃分。 應該在有線和 Wi-fi 網路上執行 QoS。

若要在您的網路上實施 QoS, 以下指導方針可協助[Microsoft 團隊中的服務品質](qos-in-teams.md)

#### <a name="proxy-servers"></a>Proxy 伺服器

許多組織會以安全性風險的方式來查看傳送給網際網路的流量, 而且會在網路上的出口端點監視及評估流量, 以緩解此風險。 Proxy 伺服器是可根據此需求部署的裝置類別。

當您執行資料包檢查或對負載進行修改時, proxy 伺服器可能會產生問題。 這可能會導致呼叫設定失敗、掛斷通話, 以及通話品質不佳。 如果即時媒體遭到強制遍歷 proxy 伺服器, 小組中的媒體堆疊將被迫傳回 TCP, 這會進一步降低品質。 UDP 總是優先于 TCP。

此外, proxy 伺服器可能不是用來處理其他載入的 Office 365, 也不是專門的 Microsoft 團隊工作負載, 包括即時媒體。

由於 proxy 伺服器可能會帶來可能的問題, 以及這些額外的容量考慮, Microsoft 建議您避開 proxy 伺服器並直接連線至 Office 365。

略過 proxy 伺服器所需的設定會因廠商而異, 但一般的方法通常會涉及更新 proxy 自動設定 (PAC) 檔案。 PAC 檔案是一個設定檔案, 說明哪些流量會透過 proxy, 以及哪些通信量會略過。

某些 proxy 伺服器廠商提供自動程式, 以確保設定是最新的。 如果您的供應商沒有提供此自動程式, 您可以從<https://aka.ms/o365proxies>下載更新的 PAC 檔案。

[小組或商務用 Skype Online 與團隊的 Proxy 伺服器](proxy-servers-for-skype-for-business-online.md)

#### <a name="firewalls"></a>道

確保正確的埠和通訊協定已開啟至所有的 Office 365 Ip, 且需要 Url 才能取得 Microsoft 團隊的存取權。 這對於高品質的部署也很重要。 只要進行通話或加入電話會議, 就能保證您的防火牆已正確設定。

如果在防火牆上只開啟 TCP, 則會建立會話, 但不會協商首選傳輸 (UDP)。 TCP 和 UDP 都必須在防火牆上開啟, 才能提供最佳的使用者體驗。

由於它具有狀態性質, 因此不適合即時媒體, 而且只會提供給 Microsoft 團隊的容錯回復網路傳輸。 在 TCP 中, 如果有資料包延遲或遺失, 那些資料包必須先重新傳輸, 直到被確認。 這可能會導致媒體資料包與即時傳送目前媒體資料包並不相關的爭用。 使用者的小組用戶端會嘗試伸展音訊, 並根據網路狀況產生可聽見的專案。 隨著 TCP 的額外額外負荷, 通常可接受的體驗會轉移到較差的使用者體驗。 基於這個原因, 需要無狀態網路傳輸 UDP。

[Office 365 url 和 IP 位址範圍](https://aka.ms/o365ips)文章中提供了開啟 Microsoft 團隊防火牆的完整指南。

在防火牆開啟之後, 您可以使用 [Microsoft 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885) 驗證雲端語音功能的連線性。

> [!IMPORTANT]
> Microsoft Office 365 IPs 和 Url 會隨著時間變更。 作為服務管理規劃的一部分, 請務必確認運作程式已就緒, 而且群組會負責監視[Office 365 url 和 IP 位址範圍](https://aka.ms/o365ips), 並據此進行更新。

#### <a name="local-internet-egress"></a>本機網際網路出口

許多網路都是用來使用中樞與輪輻拓朴的設計。 在此拓朴中, 網際網路流量通常會在 WAN (egresses) 到網際網路前, 先將 WAN 移到中央資料中心。 通常, 這是為了將網路安全裝置集中化以減少總成本的目的。

跨 WAN 的 hauling 流量會增加延遲, 並對品質和使用者體驗造成負面影響。 因為 Microsoft 團隊是在 Microsoft 大型全域網路上執行, 所以通常會有網路對等位置靠近使用者。 使用者最有可能獲得較佳的效能, 只要從當地的網際網路點 egressing 到他們的位置, 並儘快將它移到我們的語音優化網路上。 針對某些工作負荷, DNS 要求是用來傳送流量到最接近的前端伺服器。 在這種情況下, 請務必注意, 當您使用本機的出局點時, 它會與本機 DNS 解析搭配使用。

將網路路徑優化至 Microsoft 的全域網路可改善效能, 並最終為使用者提供最佳的體驗。 如需詳細資訊, 請參閱在[Office 365 中取得最佳連線和效能](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)的博客文章。

#### <a name="vpn"></a>點對點

Vpn 為許多組織提供重要的服務。 遺憾的是, 它們通常不是專為支援即時媒體而設計或設定。 某些 Vpn 可能也不支援 UDP。 Vpn 也會在已加密的媒體流量上方引入額外的加密層級。 此外, 由於將流量釘選到 VPN 裝置, 因此 Microsoft 團隊服務的連線可能無法有效。 此外, 不一定要從容量角度來設計, 以適應小組將需要的預期負載。

建議您提供一個替代路徑來避開團隊交通的 VPN。 這通常稱為分割隧道 VPN。 分割隧道表示 Office 365 的流量不會穿過 VPN, 但會直接移至 Office 365。 這項變更會對品質產生正面的影響, 但也會提供減少 VPN 裝置與組織網路負載的次要優點。

若要實現分割隧道, 請諮詢您的 VPN 供應商以取得設定詳細資料。

#### <a name="wi-fi"></a>Wi-fi

就像 VPN, Wi-fi 網路不一定設計或設定為支援即時媒體。 規劃及/或優化 Wi-fi 網路以支援小組是品質部署的重要考慮。

在優化 Wi-fi 網路時, 有幾個因素會進入播放。

- 實施 QoS 或 Wi-fi 多媒體 (WMM), 以確保媒體流量在 Wi-fi 網路上得到相應的優先順序。

- 規劃及優化 [W-Fi] 區段和存取點位置。 2.4 GHz 範圍可能會根據存取點位置提供適當的體驗, 但存取點通常會受到在該範圍中運作的其他消費者裝置的影響。 5 GHz 的範圍更適合即時媒體, 因為它們的密集範圍, 但需要更多存取點才能取得足夠的覆蓋範圍。 端點也需要支援該範圍, 並將其設定為可據此加以設定以利用這些區段。

- 如果已部署雙頻帶 Wi-fi 網路, 請考慮實施頻帶控制。 [樂隊指導委員會] 是由 Wi-fi 廠商所實施的技術, 可影響使用5Ghz 範圍的用戶端。

- 頻道交疊–當同一個頻道的存取點太靠近時, 可能會導致信號重迭並無意間爭奪, 導致使用者的體驗不佳。 確定彼此連續的存取點位於頻道上, 而不是不重迭。

每個無線廠商都有自己的部署其無線解決方案的建議。 我們建議您向您的廠商諮詢特定的指導方針。

### <a name="network-readiness-assessment"></a>網路就緒評估

網路就緒活動的一部分包括網路評量。 完成規劃與設定之後, 評等, 您可以在將使用者加入 Microsoft 團隊之前, 讓您瞭解您的網路品質。 評估結果也會協助您在啟用團隊使用者之前, 先識別並排定修正工作的優先順序。

針對在團隊中啟用雲端語音功能的所有建築物, 都應該在有線和 Wi-fi 網路上執行網路評量。

您可以使用 Microsoft 合作夥伴、協力廠商工具或[Microsoft 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885)來執行網路評量。

## <a name="plan-for-endpoint-quality"></a>規劃端點品質

在下圖中您可以看到, 端點是一個重要的構造塊, 可為使用者提供高品質的體驗。

說明![三個品質元件的圖表](media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "說明三個品質元件的圖表, 以及服務管理如何與所有三個元件重迭。將焦點放在端點上。")

Microsoft 團隊端點可以在許多裝置上執行, 包括 Pc、Mac、平板電腦和行動裝置。 此體驗的一部分不僅包括裝置, 而且使用者如何連線到裝置, 例如, 使用裝置內建的麥克風/喇叭、earbuds 或優化的耳機。 使用優化的耳機可豐富整體使用者體驗。

下列針對端點規劃的指導方針可協助您確保貴組織成功地使用團隊加入了您的組織。

### <a name="endpoint-capability"></a>端點功能

規劃中的第一個部分是確保貴組織中的所有電腦和其他裝置都能執行 Microsoft 團隊。 這涉及不只是查看硬體需求, 還需要瞭解電腦在背景執行的其他動作。 許多組織會執行其他軟體, 包括入侵偵測系統和反惡意程式碼, 這可能會影響裝置的基本效能。

Microsoft 團隊擁有可供 web、桌面 (Windows 和 Mac) 及行動裝置 (Android、iOS 和 Windows Mobile) 使用的用戶端。 如需每個平臺的軟體需求的相關資訊, 請參閱[取得 Microsoft 團隊的用戶端](get-clients.md)。

### <a name="endpoint-firewalls"></a>端點防火牆

用戶端防火牆對使用者體驗的影響可能會有很大的影響。 用戶端防火牆可能會影響通話品質, 除了可防止通話的建立。 根據[Office 365 url 和 IP 位址範圍](https://aka.ms/o365ips)中的資訊, 在用戶端防火牆上設定適當的排除。 您的協力廠商廠商將提供有關如何建立排除項的特定指導方針。

> [!NOTE]
> Microsoft 團隊會自動使用適當的防火牆設定來更新 Windows 防火牆。

### <a name="wi-fi-recommendations-for-endpoints"></a>端點的 wi-fi 建議

規劃和部署優化的 Wi-fi 網路以支援 Microsoft 團隊中的即時工作負載, 需要大量的規劃。 下列各節提供一些一般指導方針, 可協助您在規劃端點時避免一些常見的錯誤。

#### <a name="wi-fi-drivers"></a>Wi-fi 驅動程式

某些 Wi-fi 驅動程式可能會造成問題。 例如, 驅動程式在存取點之間可能會有非常嚴格的漫遊行為, 導致通話品質不佳。 這不是常見的做法, 但請務必確保電腦上的 Wi-fi 驅動程式已在部署之前更新並經過測試。

#### <a name="wi-fi-bands"></a>Wi-fi 區段

目前在 Wi-fi 裝置、2.4 GHz 和 5.0 GHz 中, 主要使用兩種類型的區段。 如果您的組織同時提供兩個頻帶, 您應該將您的驅動程式設定設定為優先使用 5.0 GHz 區段。 此區段在輸送量方面是很大的 denser, 而且受到 2.4 GHz 區段干擾的影響較小。 此建議假設您已正確優化 5.0 GHz 網路區段。

#### <a name="wi-fi-radio-type"></a>Wi-fi 無線電類型

規劃支援新版 Wi-fi 無線電類型的裝置。 如果您在您所設定的裝置上, 利用 802.11 ac 或更新版本, 就能取得良好的 Wi-fi 效能。

#### <a name="wireless-avoidance"></a>無線回避

有些組織傾向于完全避免使用 Wi-fi。 在某些情況下, 此指導方針是透過將使用者直接連線至有線網路的建議提供的。 在某些情況下, 網路系結順序可能會有最佳的無線連線, 而且即使電腦已連接至有線連線, 仍會繼續使用該連線。 若要避免此意外行為, 請設定系結順序來避免這種情況。

#### <a name="80211-power-save-protocol"></a>802.11 省電通訊協定

如果您的組織使用的無線存取點或路由器不支援802.11 節能通訊協定, 在 Windows 裝置上執行的 Microsoft 團隊中, 您可能會遇到通話中斷或太差的通話品質。 如果無法升級您的無線存取點或路由器, 您應該在以電池電源執行的裝置上更新 Windows 電源配置設定。 下列[支援文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了進一步的詳細資訊和設定指導方針。

### <a name="devices-for-teams"></a>團隊裝置

Microsoft 團隊可以用於會議或作為電話系統。 使用這些功能時, 小組所用的介面裝置在使用者體驗中起著重要的作用。

如果您使用的是內建電腦喇叭和麥克風, 擁有該設定的使用者就可能會聽到聲音。 但這些裝置通常不會針對雜訊取消進行優化, 而且任何類型的環境干擾都可能對通話中其他人產生下游影響。 利用針對這些案例優化的裝置將有助於確保高品質的體驗。

每個裝置都必須符合您的使用者需求。 您必須針對貴組織中的不同角色和使用案例, 調整裝置 (例如耳機)。 在規劃程式中應完成角色對裝置的對應練習。

選取裝置之後, 請將它們包含在最終驗證的試驗測試方案中。 在試驗期間利用調查來收集意見反應, 以確保您的裝置策略是最佳的。

目前, 我們建議使用透過商務用 Skype 認證計畫認證的音訊裝置。 若要在此程式中尋找認證的裝置, 請參閱[針對商務用 Skype 解決方案目錄認證的 USB 裝置](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)。

## <a name="client-updates"></a>用戶端更新

Microsoft 團隊的主要優點之一, 就是用戶端自動保持在最新狀態。 PC 和 Mac 上的用戶端會使用背景處理常式來更新, 在 app 空閒時檢查新的組建並下載新的用戶端。 用戶端下載大小大約為 100 MB。

組織沒有任何控制或存取原則設定來管理更新程式。 若要緩解較新組建中可能會發現之問題的風險, 最後一個已知良好的版本會保留在端點上。 如果新組建有問題, Microsoft 團隊服務可以自動將端點復原至前一個版本。

## <a name="next-steps-and-references"></a>後續步驟和參照

此表格包含一份規劃活動的摘要, 其中包含相關內容的連結。

| 圖 | 詳細資料 | 提到 |
|---|---|---|
| 規劃服務管理 | 進行操作角色對應練習 <br/> 從負責的小組中登出 <br/> 角色就緒性 | [操作指南](1-drive-value-operate-my-service.md) |
| | 提名品質的擁護者 (s) <br/> 品質擁護者準備| <br/> [品質體驗回顧指南](https://aka.ms/qerguide) |
| | 安裝品質體驗回顧範本 <br/> 上傳組建檔案 | [QERLite 範本](https://aka.ms/qertemplates) <br/> [上傳建築物資訊](turning-on-and-using-call-quality-dashboard.md)|
| 規劃網路品質 | 執行網路規劃 |  |
| | 實施 QoS | [Microsoft 團隊中的服務品質](qos-in-teams.md) |
| | 略過 proxy 伺服器 | [Proxy 指南](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) |
| | 實現分割隧道 VPN |  |
| | 針對即時媒體優化 Wi-fi 網路 | 查閱協力廠商廠商 |
| | 實施當地的網際網路出口 | [本機網際網路出口](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | 實施網路連線性 <br/> 驗證網路連線性 | [Office 365 Url 與 IP 位址](https://aka.ms/o365ips) |
| | 執行網路評量 |[網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885)  |
| 規劃端點品質 | 更新端點防火牆 | [Office 365 Url 與 IP 位址](https://aka.ms/o365ips) |
| | 驗證軟體需求 | [為 Microsoft 團隊取得用戶端](get-clients.md) |
| | 實現端點 Wi-fi 建議 | 查閱協力廠商廠商 |
| | 執行角色至裝置對應 <br/> 提供裝置並試用它們 |<br/> [裝置目錄](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |

完成規劃之後, 請繼續執行下一個步驟:[為團隊準備您的環境](https://aka.ms/SkypeToTeams-TechnicalReadiness)。
