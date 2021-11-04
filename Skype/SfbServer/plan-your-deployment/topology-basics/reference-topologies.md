---
title: 商務用 Skype Server 的參考拓撲
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: 商務用 Skype Server 的參考拓撲，包括要針對大型、中型及小型組織進行的圖表和決策。
ms.openlocfilehash: 270814a8a4dacccdec8919a0e31c9c6098603493
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762101"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>商務用 Skype Server 的參考拓撲

商務用 Skype Server 的參考拓撲，包括要針對大型、中型及小型組織進行的圖表和決策。

您的最佳商務用 Skype Server 拓撲取決於組織的規模、要部署的工作負載，以及高可用性與投資成本的喜好設定。

本節概述三個範例參考拓撲，包括在每個拓撲中考慮的眾多決策背後的理由。

## <a name="reference-topology-for-a-small-organization"></a>小型組織的參考拓撲

「小型組織」的參考拓撲顯示如何只部署三台執行商務用 Skype Server 的伺服器，來部署強大且高可用性的解決方案。

**小型組織的參考拓撲**

![部署三個伺服器圖表的參考拓撲。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **部署的 Standard Edition 伺服器成對** 此組織在其中央網站有4000使用者。 他們已部署兩部 Standard Edition 伺服器及成對搭配，以啟用高可用性和嚴重損壞修復。 每個伺服器的住宅2000使用者，但在兩部伺服器之間會同步處理所有使用者的相關資訊。 如果有一項關機，系統管理員可以將其他伺服器的使用者容錯移轉到其他伺服器，並將使用者中斷降至最低。 如需商務用 Skype Server 中高可用性和嚴重損壞修復功能的詳細資訊，請參閱[在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。

- **建議使用 Edge Server 部署。** 雖然內部 IM、出席和會議不需要部署 Edge Server，但我們仍建議小型部署使用 Edge Server。 您可以部署 Edge Server，將服務提供給目前組織防火牆以外的使用者，以達到最大的商務用 Skype Server 投資。 優點包括下列各項：

  - 貴組織的使用者可以使用商務用 Skype Server 功能（如果是在家中或在旅途中時）。

  - 您的使用者可以邀請外部使用者參與會議。

  - 如果您有也使用商務用 Skype Server 的合作夥伴、廠商或客戶組織，您可以建立與該組織的同盟關聯。 您的商務用 Skype Server 部署將會辨識來自該同盟組織的使用者，以改善共同作業。

  - 您的使用者可以與某些公用 IM 服務的使用者交換立即訊息。

- **分支網站生存能力。** 此組織正在執行商務用 Skype Server 的企業語音功能的試驗計畫。 有些使用者使用商務用 Skype Server 作為其唯一的語音方案。 有些企業語音試驗使用者位於分支網站。 分支網站沒有可靠的廣域網路絡 (WAN) 連結至中央網站，因此會在該處部署 Survivable 分支裝置。 在部署此功能的情況下，如果 WAN 連結停機，分支網站上的使用者仍可撥打和接聽通話 (組織中的呼叫和 PSTN 通話) 、具有語音信箱功能，以及透過兩方立即訊息 (IM) 進行通訊。 無法使用 WAN 連結時，也可以驗證使用者。 如需詳細資訊，請參閱[Plan for 企業語音韌性 in 商務用 Skype Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。

- **Exchange UM 部署。** 此參考拓撲包括執行 Microsoft Exchange Server 的 Exchange 整合通訊 (UM) Server，而不是商務用 Skype Server。

- **OfficeWeb Apps Server。** 建議您在使用 Web 會議的每家組織中部署 Office 網頁應用程式伺服器或 Office Web apps server 伺服器陣列。 Officeweb Apps Server 可以在 web 會議中呈現 PowerPoint 的投影片。

## <a name="reference-topology-for-a-medium-organization"></a>中型組織的參考拓撲

具有高可用性和單一資料中心的參考拓撲是專為具有一個中央網站的中小型組織所設計。 下圖中的實際拓撲是針對20000使用者的組織。

**中型組織的參考拓撲**

![單一資料中心圖表的參考拓撲。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **新增更多前端伺服器來容納更多使用者。** 此圖中的實際拓撲有三部前端伺服器，可為20000使用者提供支援。 如果您有單一的中央網站和更多使用者，您只需要將多部前端伺服器新增至集區即可。 每個集區的使用者數目上限為80000，含十二部前端伺服器。

    不過，如果在網站再新增一個前端集區，則單一個網站拓撲可以支援更多使用者。

- **可以新增災難修復。** 針對此組織，其商務用 Skype Server 服務的高可用性是必要的功能，但不會復原災難修復。 其部署的前端伺服器集區提供高可用性。

    如果他們想要新增嚴重損壞復原能力，他們可能會考慮建立另一個資料中心，並在其中新增另一個前端集區，並將它與目前資料中心的前端集區配對。 然後，如果發生嚴重影響其主要集區的嚴重損壞，系統管理員可以將使用者容錯移轉至備份組區。

- **後端伺服器已鏡像** 若要提供更高的基本使用者功能可用性，該組織已為每一個前端集區部署一組鏡像的後端伺服器。

- **監控伺服器資料庫選項。** 此組織已部署監控，以確保企業語音通話的品質，並 A/V 會議。 監控是部署于每一部前端伺服器上，而監視資料庫則是與後端伺服器組合。 我們也支援監控資料庫位於不同伺服器上的拓撲。

- **Edge Server 高可用性** 在此範例中，有20000位使用者的組織，只有一部 Edge Server 足以獲得效能。 不過，他們已部署兩部伺服器的集區，以提供高可用性。

- **分支網站部署選項。** 此拓撲中的組織部署了企業語音作為語音解決方案。 分支網站1沒有具有彈性廣域網路絡的 (WAN) 連結至中央網站，因此它已部署 Survivable 分支裝置以維護許多商務用 Skype Server 功能，以防中央網站的 WAN 連結停止運作。 不過，分支網站 2 具有可恢復的 WAN 連結，因此只需要有公用交換電話網路 (PSTN) 閘道。 此網站部署的 PSTN 閘道支援媒體旁路，所以分支網站 2 不需要有中繼伺服器。 如需詳細資訊，請參閱[Plan for 企業語音韌性 in 商務用 Skype Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。

- **DNS 負載平衡。** 前端集區和 Edge Server 集區，具有部署 SIP 流量的 DNS 負載平衡。 如此一來，Edge Server 就不需要硬體負載平衡器，這樣可大幅減少為其他集區安裝和維護硬體負載平衡器的工作，因為只有 HTTP 流量才需要硬體負載平衡器。 如需詳細資訊，請參閱 [DNS 負載平衡](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)。

- **Exchange UM 部署。** 此參考拓撲包括執行 Microsoft Exchange Server 的 Exchange 整合通訊 (UM) Server，而不是商務用 Skype Server。

- **OfficeWeb Apps Server。** 建議您在使用 Web 會議的每家組織中部署 Office 網頁應用程式伺服器或 Office Web apps server 伺服器陣列。 OfficeWeb Apps Server 可讓 Powerpoint 投影片呈現在 web 會議中。

- **可以新增 director。** 如果此組織想要協助提高安全性以防範拒絕服務攻擊，也可以部署 Director 集區。 Director 是商務用 Skype Server 中不會家用使用者帳戶或提供目前狀態或會議服務的個別、選用的伺服器角色。 它充當內部的下一個躍點伺服器，Edge Server 會將傳入 SIP 流量路由傳送至內部伺服器。 Director 對輸入要求進行預先驗證，並將它們重新導向至使用者的主集區或伺服器。 Director 的預先驗證可讓您從部署中未知的使用者帳戶中丟棄要求。 Director 可協助將前端伺服器與惡意流量（如拒絕服務 (DoS) 攻擊）隔離。 如果網路在這類攻擊中以不正確外部流量淹沒，該流量會結束于 Director。

- **System Center建議使用 Operations Manager。** 建議您監視商務用 Skype Server 部署的健康情況，以協助確保使用者的服務可用性。 您可以使用 System Center Operations Manager 管理元件，以取得可免費從 Microsoft 下載商務用 Skype。 使用商務用 Skype 管理元件，您可以在發生問題時主動取得即時警示、執行綜合交易，以測試端對端商務用 Skype 功能、取得服務可用性的報告等等。 這可協助您在使用者體驗之前，主動回應部署的問題。

## <a name="reference-topology-for-a-large-organization"></a>大型組織的參考拓撲

具有多個資料中心支援之大型組織的參考拓撲，適用于具有多部中央網站的組織規模。 下圖中的實際拓撲是針對50000使用者的組織，其中的20000使用者在中央網站 A，20000位於中央網站 B。中央網站 C 和分支網站上的總10000。 此圖表所顯示的拓撲類型可容納具有任意數目使用者的組織。

除了前端伺服器集區所提供的高可用性之外，此拓撲還會新增嚴重損壞修復支援。 中央網站 A 和 B 的前端集區會成對搭配。 如果其中一個集區中斷，系統管理員可以將受影響使用者的服務移至未受影響之網站的配對集區。

這種拓撲會顯示在多個圖表中，並優先于中央網站的詳細視圖。

**具有多個資料中心之大型組織的參考拓撲概述**

![多個資料中心的參考拓撲。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**大型組織的參考拓撲：中央網站 A 的詳細視圖**

![拓撲3-2。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**大型組織的參考拓撲：中央網站 B 的詳細視圖**

![拓撲3-3。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**大型組織的參考拓撲：中央網站 C 的詳細視圖**

![拓撲3-4。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **前端集區配對以啟用嚴重損壞修復。** 網站 A 和網站 B 的前端集區彼此配對，以提供嚴重損壞修復支援。 如果某個網站上的集區失敗，系統管理員可以從該網站將使用者容錯移轉至另一個網站的配對前端集區，並為使用者最低的服務中斷。 這兩個前端集區共有六部伺服器，也足以用於兩個集區中的所有40000使用者，以防容錯移轉。 如需詳細資訊，請參閱[商務用 Skype Server 中的計畫高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。

- **後端伺服器已鏡像** 若要提供更高的基本使用者功能可用性，該組織已為每一個前端集區部署一組鏡像的後端伺服器。 這是選用的拓撲，而您可以選擇部署單一後端伺服器。 也支援 SQL 叢集及 AlwaysOn 可用性群組。 如需詳細資訊，請參閱[商務用 Skype Server 中的後端伺服器高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。

- **在分支網站上使用 Standard Edition 伺服器。** 此組織會將網站 C 視為分支網站，因為它只有600名員工。 不過，使用者彼此之間有許多 A/V 會議。 如果它是以分支網站形式部署在商務用 Skype Server 中，則這些會議的媒體會在廣域網路絡上執行 (WAN) 至已部署前端伺服器的中央網站。 為了避免發生這種可能的頻寬負載，已在此網站上安裝一對 Standard Edition 伺服器，這會裝載這些會議。 而且由於 Standard Edition 伺服器已安裝在那裡，依定義商務用 Skype Server 會將它視為中央網站，在拓撲產生器和規劃工具中則會被視為這類功能。

    在這裡，只要一部 Standard Edition 伺服器就能達到效能，但組織已部署兩部以上的伺服器，以提供高可用性，以防一部伺服器已停機。

    雖然網站 C 被視為中央網站，但您不需要在此部署 Edge Server。 在此範例中，Site C 會使用部署于網站 A 的 Edge Server。

- **監視與** 封存此組織已同時部署監控與封存。 當您部署監控或封存時，它會在每一部前端伺服器上執行。 這些功能的資料庫可以與後端資料庫組合，也可以位於不同的伺服器上。 此組織已將這些資料庫放在與後端伺服器不同的伺服器上（位於中央網站 B）。資料庫這裡會從所有網站中的前端伺服器接收監控和封存資料。

- **分支網站部署選項。** 此組織實際上具有超過50個分支網站，詳細資訊圖表中只會顯示兩個分支網站。 分支網站1沒有指向中央網站的彈性 WAN 連結，因此他們已部署 Survivable 分支裝置以提供電話語音，以防中央網站的 WAN 連結停止運作。 分支網站2不過具有彈性 WAN 連結，因此只需要公用交換電話網路 (PSTN) 閘道。 此網站部署的 PSTN 閘道支援媒體旁路，所以分支網站 2 不需要有中繼伺服器。 如需決定在分支網站安裝之專案的詳細資訊，請參閱[Plan for 企業語音韌性 in 商務用 Skype Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。

- **SIP 主幹和轉送伺服器。** 請注意，在中央網站 B 上，轉送伺服器不會與前端伺服器組合。 這是因為針對使用 SIP 主幹的網站，建議使用獨立的轉送伺服器。 在其他大多數的情況下，我們建議您組合轉送伺服器與前端伺服器。 如需有關轉送伺服器拓撲的詳細資訊，請參閱規劃檔中的中繼 [伺服器元件和拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-mediation-server) 。

- **部署持續性聊天。** 此組織已部署啟用持續性聊天所需的伺服器。 它已部署多個持續性聊天前端伺服器來處理集區中使用者數目的負載，並提供高可用性。 它也部署了持續性聊天的相容性，並已在不同的伺服器上找到 Persistent chat Store 和 Persistent Chat 規範存放區。 這些存放區可能是組合，甚至可以與後端伺服器組合，但這項組織已選擇將其分開，以提供更好的效能。

    > [!NOTE]
    > 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。

- **DNS 負載平衡。** 前端集區和 Edge Server 集區使用 DNS 負載平衡。 這樣就不需要對 Edge Server 的內部介面進行硬體負載平衡器，也能大幅減少對其他集區的硬體負載平衡器進行設定與維護所需花費的時間，因為只有 HTTP 流量需要硬體負載平衡器。 如需詳細資訊，請參閱 (。/../plan-your-deployment/network-requirements/load-balancing.md # BKMK_DNSLoadBalancing) 。

- **Exchange UM 部署。** 商務用 Skype Server 可搭配內部部署 Exchange 整合通訊 (um) 和主控 Exchange um。 中央網站 A 包含以執行 Microsoft Exchange Server 的 Exchange 整合通訊 (UM) Server，而不是商務用 Skype Server。 商務用 Skype Server 在前端集區上執行的 Exchange UM 功能。

    中央網站 B 使用主控的 Exchange，因此也會主控 Exchange UM 伺服器功能。

    如需 Exchange UM 的詳細資訊，請參閱規劃檔中的[On-Premises Exchange 整合通訊整合](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration)及[主控 Exchange 整合通訊整合](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)。

- **OfficeWeb Apps Server。** 建議您在使用 Web 會議的每家組織中部署 Office 網頁應用程式伺服器或 Office Web apps server 伺服器陣列。 您可以在一個網站中部署單一 Office Web Apps Server 伺服器陣列，以便從所有網站提供流量，或在每個網站中部署流量。 OfficeWeb Apps Server 可讓 Powerpoint 投影片呈現在 web 會議中。

- **可以新增 director。** 如果此組織想要提高安全性以防範拒絕服務攻擊，也可以部署 Director 集區。 Director 是商務用 Skype Server 中不會家用使用者帳戶或提供目前狀態或會議服務的個別、選用的伺服器角色。 它充當內部的下一個躍點伺服器，Edge Server 會將傳入 SIP 流量路由傳送至內部伺服器。 Director 對輸入要求進行預先驗證，並將它們重新導向至使用者的主集區或伺服器。 Director 的預先驗證可讓您從部署中未知的使用者帳戶中丟棄要求。 Director 可協助將前端伺服器與惡意流量（如拒絕服務 (DoS) 攻擊）隔離。 如果網路在這類攻擊中以不正確外部流量淹沒，該流量會結束于 Director。

- **System Center建議使用 Operations Manager。** 建議您監視商務用 Skype Server 部署的健康情況，以協助確保使用者的服務可用性。 您可以使用 System Center Operations Manager 管理元件，以取得可免費從 Microsoft 下載商務用 Skype。 使用商務用 Skype 管理元件，您可以在發生問題時主動取得即時警示、執行綜合交易，以測試端對端商務用 Skype 功能、取得服務可用性的報告等等。 這可協助您在使用者體驗之前，主動回應部署的問題。