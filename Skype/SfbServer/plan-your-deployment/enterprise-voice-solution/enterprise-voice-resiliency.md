---
title: 在 商務用 Skype Server 中規劃企業語音復原
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: 瞭解如何在中央網站和分支網站上支援商務用 Skype Server 企業語音的語音恢復功能。 分支網站選項包括部署 Survivable Branch Appliance 或 Survivable Branch Server。
ms.openlocfilehash: 493f599f7fbec2a67efaaf59851fd7c2f3b2d144
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675475"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>在 商務用 Skype Server 中規劃企業語音復原

瞭解如何在中央網站和分支網站上支援商務用 Skype Server 企業語音的語音恢復功能。 分支網站選項包括部署 Survivable Branch Appliance 或 Survivable Branch Server。

語音復原是指當裝載商務用 Skype Server的中央網站無法使用時，使用者能夠繼續撥打和接聽電話，不論是透過廣域網路 (WAN) 失敗或其他原因。 如果中央月臺失敗，企業語音服務必須透過無縫容錯移轉至備份月臺，繼續不中斷。 萬一發生 WAN 失敗時，必須將分支月臺呼叫重新導向至本機 PSTN 閘道。 本節討論在中央網站或 WAN 失敗時的語音恢復功能規劃。

## <a name="central-site-resiliency"></a>中央網站復原

越來越多的企業開始將網站散佈到全球各地。 維護緊急服務、存取技術支援人員，以及在中央網站服務中斷時執行重要商務工作的能力，對於任何企業語音復原解決方案而言都是不可或缺的。 當中央網站無法使用時，必須符合下列條件：

- 必須提供語音容錯移轉功能。

- 通常向中央網站的前端集區註冊的使用者必須能夠向替代的前端集區註冊。 這可以透過建立多個 DNS SRV 記錄來完成，每個記錄都會解析為每個中央網站中的目錄集區或前端集區。 您可以調整 SRV 記錄的優先順序和權數，讓由該中央網站提供服務的使用者取得對應的 Director 和前端集區，而在其他 SRV 記錄中的前端集區前面。

- 撥入其他網站或由其他網站撥出的使用者通話必須重新路由至 PSTN。

本主題說明保障中央網站語音恢復能力的建議解決方案。

### <a name="architecture-and-topology"></a>架構與拓撲

在中央網站規劃語音恢復功能需要基本瞭解商務用 Skype Server註冊機構在啟用語音容錯移轉時所扮演的中央角色。 商務用 Skype Server註冊機構是一項服務，可啟用用戶端註冊和驗證，並提供路由服務。 它會在所有Standard Edition伺服器、前端伺服器、Director 或 Survivable Branch Appliance 上執行。 註冊機構集區是由在前端集區上執行且位於相同月臺的註冊機構服務所組成。 商務用 Skype用戶端會透過下列探索機制探索前端集區：

1. DNS SRV 記錄

2. 自動探索 Web 服務

3. DHCP 選項 120

在商務用 Skype用戶端連線到前端集區之後，負載平衡器會將其導向集區中的其中一個前端伺服器。 該前端伺服器接著會將用戶端重新導向至集區中慣用的註冊機構。

針對企業語音啟用的每個使用者都會指派給特定的註冊機構集區，這會變成該使用者的主要註冊機構集區。 在特定網站上，數百名或數千名使用者通常會共用單一主要登錄器集區。 為了針對任何一個分支網站裡倚賴中央網站以獲得顯示狀態、會議或容錯移轉功能的使用者，記錄其對中央網站資源的使用情況，建議您將每位分支網站使用者視為向中央網站註冊的使用者。 分支網站使用者的數目目前沒有任何限制，包括向 Survivable Branch Appliance 註冊的使用者。

為了確保中央網站故障時的語音恢復能力，主要登錄器集區必須在另一個網站上設有一台指定的備份登錄器集區。 您可以使用拓撲產生器復原設定來設定備份。 假設兩個網站之間存在可恢復的 WAN 連結，則已無法再使用主要登錄器集區的使用者會自動導向至備用登錄器集區。

下列步驟說明用戶端探索與註冊程序：

1. 用戶端會透過 DNS SRV 記錄探索商務用 Skype Server。 在商務用 Skype Server中，DNS SRV 記錄可以設定為將多個 FQDN 傳回 DNS SRV 查詢。 例如，如果 Contoso 企業擁有三個中央網站 (北美、歐洲與亞太地區) 並在每個中央網站擁有一個 Director 集區，DNS SRV 記錄可以分別指向這三個位置的個別 Director 集區 FQDN。 只要其中一個位置中的 Director 集區可供使用，用戶端就可以連線到第一個躍點商務用 Skype Server。

    > [!NOTE]
    > 使用 Director 集區是選擇性的。 您可以改用前端集區。

2. Director 集區會通知商務用 Skype用戶端有關使用者的主要註冊機構集區和備份登錄器集區。

3. 商務用 Skype用戶端會先嘗試連線到使用者的主要註冊機構集區。 如果主要登錄器集區有回應，該登錄器就會接受註冊。 如果主要登錄器集區無法使用，商務用 Skype用戶端會嘗試連線到備份註冊機構集區。 如果備份登錄器集區可用，且已藉由偵測到指定容錯移轉間隔缺少活動訊號， (判斷使用者的主要登錄器集區無法使用，) 備份註冊機構集區接受使用者的註冊。 備份註冊機構偵測到主要登錄器再次可用之後，備份登錄器集區會將容錯移轉用戶端重新導向至其主要集區。

### <a name="requirements-and-recommendations"></a>需求和建議

以下為大多數組織在實作中央網站語音恢復能力時適用的需求與建議事項：

- 主要與備份登錄器集區所屬網站必須由可恢復的 WAN 連結來串連。

- 每個中央網站必須內含一個登錄器集區，且該集區必須包含一或多個登錄器。

- 每個註冊機構集區都必須使用 DNS 負載平衡、硬體負載平衡或兩者進行負載平衡。 如需規劃負載平衡設定的詳細資訊，請參閱[商務用 Skype的負載平衡需求](../../plan-your-deployment/network-requirements/load-balancing.md)。

- 必須使用 商務用 Skype Server Management Shell **set-CsUser** Cmdlet 或 商務用 Skype Server 主控台，將每個使用者指派給主要登錄器集區。

- 主要登錄器集區必須在其他中央網站設有一個備份登錄器集區。

- 主要登錄器集區必須設為容錯移轉至備份登錄器集區。 主要登錄器集區預設會在故障超過 300 秒之後容錯移轉至備份登錄器集區。 您可以使用 商務用 Skype Server 拓撲產生器來變更此間隔。

- 設定容錯移轉路由。 設定路由時，所指定的閘道必須與主要路由之指定閘道分屬不同網站。

- 如果中央月臺包含您的主要管理伺服器，而且月臺可能會長時間關閉，您必須在備份月臺重新安裝管理工具;否則，您將無法變更任何管理設定。

### <a name="dependencies"></a>相依性

商務用 Skype Server取決於下列基礎結構和軟體元件，以確保語音恢復：

|**元件** <br/> |**功能** <br/> |
|:-----|:-----|
|DNS  <br/> |負責解析 SRV 記錄與 A 記錄以因應伺服器對伺服器，及伺服器對用戶端的連線需求  <br/> |
|Exchange 與 Exchange Web 服務 (EWS)  <br/> |連絡儲存裝置；行事曆資料  <br/> |
|Exchange 整合通訊與 Exchange Web 服務  <br/> |通話記錄、語音信箱清單、語音信箱  <br/> |
|DHCP 選項 120  <br/> |如果無可用的 DNS SRV，用戶端會嘗試使用 DHCP 選項 120 來探索登錄器。 若要讓此功能能夠運作，必須設定 DHCP 伺服器，或商務用 Skype Server必須啟用 DHCP。  <br/> |

### <a name="survivable-voice-features"></a>Survivable Voice 功能

如果先前的需求與建議都實作完畢，則備份登錄器集區會提供下列語音功能：

- 撥出 PSTN 電話

- 撥入 PSTN 電話，前提是電話語音服務提供者支援容錯移轉至備份網站的功能

- 相同與不同的網站之間的使用者，皆可進行企業通話

- 基本通話處理，包括通話保留、取回和轉接

- 兩方立即訊息及相同網站的使用者之間共用音訊與視訊功能

- 來電轉接、端點同時響鈴、通話委派與小組通話服務，但前提是同一個網站裡通話委派的雙方或所有小組成員都有這些設定。

- 現有的電話與用戶端將繼續運作。

- 詳細通話記錄 (CDR)

- 驗證與授權

依據這些功能的設定方式，當主要中央網站無法提供服務時，以下語音功能不一定能夠發揮功用：

- 語音信箱儲放與接聽

    如果您想在主要中央網站中斷服務時提供 Exchange UM 服務的話，必須執行下列其中一個步驟：

  - 變更 DNS SRV 記錄，以便中央網站的 Exchange UM 伺服器指向另一個網站的備份 Exchange UM 伺服器。

  - 將每個使用者的Exchange UM 撥號對應表設定為在中央月臺和備份月臺包含Exchange UM 伺服器，但將備份Exchange UM 伺服器指定為已停用。 如果主要月臺變得無法使用，Exchange系統管理員必須將備份月臺上的Exchange UM 伺服器標示為已啟用。

    如果上述解決方案都無法使用，則在中央網站無法使用時，將無法使用Exchange UM。

- 所有會議類型

    已經容錯移轉至備份網站的使用者，可以加入由開放使用集區的召集人所建立或主控的會議，但是由於該使用者所屬的主要集區已經不再提供服務，因此無法自行建立或主控會議。 同樣地，其他使用者無法加入在受影響使用者的主要集區上主持的會議。

下列語音功能在主要中央網站中斷服務時將無法運作：

- 會議自動語音應答

- 顯示狀態與 DND 基礎路由

- 更新來電轉接設定

- 回應群組服務和通話駐留

- 佈建新電話與用戶端

- 通訊錄 Web 搜尋

## <a name="branch-site-resiliency"></a>分支月臺復原

如果您想要提供分支月臺復原功能，也就是高可用性企業語音服務，您有三個選項可執行這項操作：

- Survivable Branch Appliance

- Survivable Branch Server

- 分支月臺的完整商務用 Skype Server部署

此指南會協助您評估最適合您組織的恢復能力解決方案，以及根據恢復能力解決方案，評估要使用的 PSTN 連線解決方案。也會協助您說明先決條件及其他規劃考量，以準備部署選擇的解決方案。

### <a name="branch-site-resiliency-features"></a>分支月臺復原功能

如果您提供分支月臺復原功能，如果分支月臺與中央網站的 WAN 連線失敗，或中央網站無法連線，則應繼續提供下列語音功能：

- 輸入和輸出公用交換電話網路 (PSTN) 電話

- 相同與不同的網站之間的使用者，皆可進行企業通話

- 基本通話處理，包括通話保留、取回和轉接

- 兩方立即訊息

- 呼叫轉送、端點同時響鈴、通話委派和小組通話服務，但前提是委派者和委派 (例如，管理員和經理的系統管理員) 或所有小組成員都設定在同一個月臺

- CDR () 的通話詳細資料記錄

- 使用會議自動語音應答的 PSTN 撥入式會議

- 如果您設定語音信箱重新路由設定，則可使用語音信箱功能。

- 使用者驗證和授權

只有當復原解決方案是分支月臺的完整商務用 Skype Server部署時，才能使用下列功能：

- IM、Web 和 A/V 會議

- 目前狀態和不打擾 (以 DND) 為基礎的路由 (，其中會防止在已啟用 DND 的擴充功能上撥打電話) 

- 更新來電轉接設定

- 回應群組應用程式和通話駐留應用程式

- 布建新的電話和用戶端，但只有在分支月臺有Active Directory 網域服務時才會布建。

- 增強型 9-1-1 (E9-1-1) 

    如果已部署 E9-1-1，而且因為 WAN 連結已關閉，所以無法使用中央網站的 SIP 主幹，則 Survivable Branch Appliance 會將 E9-1-1 呼叫路由傳送至本機分支閘道。 若要啟用這項功能，分支網站使用者的語音原則應該在 WAN 失敗時，將呼叫路由傳送至本機閘道。

> [!NOTE]
> XMPP 不支援 SBA (代理分公司) 。 位於 SBA 設定中的使用者將無法傳送 IM 或查看具有 XMPP 連絡人的目前狀態。

### <a name="branch-site-resiliency-solutions"></a>分支月臺復原解決方案

為您的組織提供分支網站恢復能力的好處是顯而易見的。 具體來說，如果您失去與中央網站的連線，分支網站使用者會繼續擁有企業語音服務和語音信箱 (如果您設定語音信箱重新路由設定) 。 但對於使用者人數低於 25 位的網站而言，恢復能力解決方案所提供的投資報酬率可能不夠。

如果您決定要提供分支網站恢復能力，您有三個選項。下表可協助您判斷最適合您的組織之選項。

|**如果您...**|**我們建議您使用...**|
|:-----|:-----|
|在您的分支網站上主控 25 到 1000 名使用者，且投資報酬率不足以支應完整部署，或是不具本機管理支援  <br/> |Survivable Branch Appliance  <br/> Survivable Branch Appliance 是業界標準的刀鋒伺服器，商務用 Skype Server註冊機構和轉送伺服器在 Windows Server 2008 R2 上執行。 Survivable Branch Appliance 也包含公用交換電話網路 (PSTN) 閘道。 合格的第三方裝置 (由參與 Survivable Branch Appliance (SBA) 資格/認證方案的 Microsoft 協力廠商所開發) 在 WAN 失效時仍可提供持續的 PSTN 連線，但這個方法無法提供可恢復的顯示狀態與會議功能，因為這些功能依存於中央網站上的前端伺服器。  <br/> For details about Survivable Branch Appliances, see "Survivable Branch Appliance Details," later in this topic.  <br/> **注意：** 如果您也決定搭配 Survivable Branch Appliance 使用 SIP 主幹，請連絡您的 Survivable Branch Appliance 廠商，以瞭解哪個服務提供者最適合您的組織。 <br/> |
|在您的分支網站裝載 1000 到 2000 位使用者、缺少復原的 WAN 連線，並已訓練商務用 Skype Server系統管理員可用  <br/> |Survivable Branch Server 或兩個 Survivable Branch Appliance。  <br/> Survivable Branch Server 是符合指定硬體需求的Windows伺服器，其上已安裝商務用 Skype Server註冊機構和轉送伺服器軟體。 該伺服器必須將 PSTN 閘道或 SIP 主幹連線至電話服務提供者。  <br/> For details about Survivable Branch Servers, see "Survivable Branch Server Details," later in this topic.  <br/> |
|如果您除了最多 5000 位使用者的語音功能之外，還需要出席和會議功能，且已訓練商務用 Skype Server系統管理員可用  <br/> |以 Standard Edition Server 部署為中央網站，而非分支網站。  <br/> 完整商務用 Skype Server部署提供連續的 PSTN 連線，以及萬一發生 WAN 失敗時的復原狀態和會議。  <br/> |

#### <a name="resiliency-topologies"></a>恢復能力拓撲

下圖顯示分支網站恢復能力所適用的建議拓撲。

**分支網站恢復能力選項**

![語音分支復原選項。](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance 詳細資料

商務用 Skype Server Survivable Branch Appliance 包含下列元件：

- 使用者驗證、登錄與通話路由所需的登錄器

- 用以處理登錄器與 PSTN 閘道間往來訊號的中繼伺服器

- 在 WAN 中斷時，用以將通話路由至 PSTN 作為後援傳輸的 PSTN 閘道

- 供本機使用者存放資料的 SQL Server Express

Survivable Branch Appliance 也包含 PSTN 主幹、類比埠和乙太網路介面卡。

如果分支網站與中央網站的 WAN 連線變得無法使用，內部分支使用者會繼續向 Survivable Branch Appliance 註冊機構註冊，並使用與 PSTN 的 Survivable Branch Appliance 連線來取得不中斷的語音服務。 當分支網站的 WAN 連結無法使用時，從家中或其他遠端位置連線的分支網站使用者將可使用中央網站上的登錄器伺服器進行登錄。 這些使用者將可擁有完整的整合通訊功能，但有一例外，傳入分支網站的來電會轉接至語音信箱。 當 WAN 連線恢復時，分支網站使用者即應可重獲完整的功能。 容錯移轉至 Survivable Branch Appliance 或還原服務都不需要 IT 系統管理員。

商務用 Skype Server在分支網站最多支援兩個 Survivable Branch Appliance。

#### <a name="survivable-branch-appliance-deployment-overview"></a>Survivable Branch Appliance 部署概觀

Survivable Branch Appliance 是由原始設備製造商與 Microsoft 合作製造，並由增值零售商代表他們部署。 只有在中央月臺已部署商務用 Skype Server、分支網站的 WAN 連線已就緒，且分支月臺使用者已啟用企業語音之後，才會進行此部署。

如需這些階段的詳細資訊，請參閱部署文件中的＜[Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server)＞。

|**階段**|**步驟**|**使用者權限**|
|:-----|:-----|:-----|
|設定 Survivable Branch Appliance 的Active Directory 網域服務  <br/> |**在中央網站上：** <br/>  為將在分支月臺安裝並啟用 Survivable Branch Appliance 的技術人員建立網域使用者帳戶 (或企業身分識別) 。 <br/>  在 Active Directory 網域服務 中，使用適用的完整功能變數名稱 (FQDN) ) 建立適用于 Survivable Branch Appliance 的電腦帳戶 (。 <br/>  在拓撲產生器中，建立併發布 Survivable Branch Appliance。 <br/> |技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。 Survivable Branch Appliance 必須屬於 RTCSBAUniversalServices 群組，這會在您使用拓撲產生器時自動發生。  <br/> |
|安裝並啟用 Survivable Branch Appliance。  <br/> |**在分支網站上：** <br/>  連線 Survivable Branch Appliance 連線到乙太網路埠和 PSTN 埠。 <br/>  啟動 Survivable Branch Appliance。 <br/>  使用為中央網站的 Survivable Branch Appliance 建立的網域使用者帳戶，將 Survivable Branch Appliance 加入網域。 設定 FQDN 與 IP 位址，使其符合在電腦帳戶中建立的 FQDN。 <br/>  使用 OEM 使用者介面設定 Survivable Branch Appliance。 <br/>  測試 PSTN 連線。 <br/> |技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。  <br/> |

#### <a name="survivable-branch-server-details"></a>Survivable Branch Server 詳細資料

在 [拓撲產生器] 中建立分支月臺，將 Survivable Branch Server 新增至該月臺，然後在您要安裝角色的電腦上執行 [商務用 Skype Server 部署精靈]。

### <a name="branch-site-resiliency-requirements"></a>分支月臺復原需求

本主題將協助您為使用者準備分支網站復原能力和語音信箱生存能力，並同時指定相關的硬體和軟體需求。

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>準備分支使用者以Branch-Site復原

將使用者的註冊機構集區設定為 Survivable Branch Appliance (SBA) 或 Survivable Branch Server，讓使用者準備好進行分支網站復原。

#### <a name="registrar-assignments-for-branch-users"></a>分支使用者的註冊機構指派

無論您選擇哪一個分支月臺復原解決方案，您都必須將主要註冊機構指派給每個使用者。 無論註冊機構位於 Survivable Branch Appliance、Survivable Branch Server 或獨立商務用 Skype Server Standard 或 Enterprise Edition 伺服器中，分支網站使用者都應該一律向分支網站註冊註冊機構。 需要網域名稱系統 (DNS) 服務 (SRV) 資源記錄，讓用戶端可以探索其註冊機構集區。 如果 Survivable Branch Appliance 變得無法使用，這就是分支月臺用戶端自動探索備份註冊機構的方式。

如果分支月臺沒有 DNS 伺服器，則有兩種設定 Survivable Branch Appliance 或 Survivable Branch Server 探索的替代方式：

- 在分支月臺的動態主機設定通訊協定 (DHCP) 伺服器上設定 DHCP 選項 120，以指向 Survivable Branch Appliance 或 Survivable Branch Server 的 FQDN) 完整功能變數名稱 (。

- 設定 Survivable Branch Appliance 或 Survivable Branch Server 以回應 DHCP 120 查詢。

#### <a name="voice-routing-for-branch-users"></a>分支使用者的語音路由

建議您為分支網站中的使用者建立個別的使用者層級語音透過網際網路通訊協定 (VoIP) 原則。 此原則應包含使用 Survivable Branch Appliance 或分支伺服器閘道的主要路由，以及一或多個使用主幹與公用交換電話網路絡的備份路由 (中央月臺的 PSTN) 閘道。 如果主要路由無法使用，則會改用使用一或多個中央月臺閘道的備份路由。 如此一來，不論使用者在何處註冊—在分支網站註冊機構或中央網站的備份註冊機構集區上—使用者的 VoIP 原則一律有效。 這是容錯移轉案例的重要考慮。 例如，如果您需要重新命名 Survivable Branch Appliance，或重新設定 Survivable Branch Appliance 以連線到中央網站的備份註冊機構集區，則必須在持續期間內將分支月臺使用者移至中央網站。  (如需重新命名或重新設定 Survivable Branch Appliance 的詳細資訊，請參閱部署檔中的 [附錄 B：管理 Survivable Branch Appliance](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) 。) 如果這些使用者沒有使用者層級 VoIP 原則或使用者層級撥號對應表，當使用者移至另一個網站時，預設會套用中央網站的月臺層級 VoIP 原則和月臺層級撥號對應表， 而不是分支月臺月臺層級 VoIP 原則和撥號對應表。 在此案例中，除非備份註冊機構集區所使用的月臺層級 VoIP 原則和月臺層級撥號對應表也可以套用至分支網站使用者，否則他們的呼叫將會失敗。 例如，如果位於日本分支網站的使用者移至 Redmond 中的中央網站，則在所有 7 位數呼叫前面加上 +1425 的正規化規則的撥號對應表不太可能能適當地轉譯這些使用者的通話。

> [!IMPORTANT]
> 當您建立分公司備份路由時，建議您將兩個 PSTN 電話使用量記錄新增至分公司使用者原則，並將個別的路由指派給每個路由。 第一個或主要路由會將呼叫導向至與 Survivable Branch Appliance (SBA) 或分支伺服器相關聯的閘道;第二個或備份路由會將呼叫導向中央月臺的閘道。 在指示呼叫中，SBA 或分支伺服器會嘗試指派給第一個 PSTN 使用量記錄的所有路由，然後再嘗試第二筆使用量記錄。

為了協助確保在分支閘道或 Survivable Branch Appliance 網站的Windows元件無法使用時，對分支月臺使用者的輸入呼叫會連線到這些使用者 (發生這種情況。 例如，如果 Survivable Branch Appliance 或分支閘道已關閉進行維護) ，請在閘道上建立容錯移轉路由 (或使用您的直接向內撥號 (DID) 提供者) 將連入呼叫重新導向至備份中央網站的註冊機構集區。 從該處，呼叫會透過 WAN 連結路由傳送至分支使用者。 請確定路由會轉譯號碼，以符合 PSTN 閘道或其他主幹對等互連接受的電話號碼格式。 如需建立容錯移轉路由的詳細資訊，請參閱設定 [容錯移轉路由](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route)。 此外，在分支月臺為與閘道相關聯的主幹建立服務層級撥號對應表，以將來電正規化。 如果您在分支月臺上有兩個 Survivable Branch Appliance，您可以為這兩者建立月臺層級撥號對應表，除非需要個別的服務層級方案。

> [!NOTE]
> 若要考慮依賴中央網站來進行會議、會議或容錯移轉的任何分支網站使用者使用中央網站資源，建議您將每個分支網站使用者視為已向中央網站註冊。 分支網站使用者的數目目前沒有任何限制，包括向 Survivable Branch Appliance 註冊的使用者。

我們也建議您建立使用者層級撥號對應表和語音原則，然後將它指派給分支網站使用者。 如需詳細資訊，請參閱部署檔[中的在 商務用 Skype Server 中建立或修改撥號對應表](../../deploy/deploy-enterprise-voice/dial-plans.md)和[建立分支使用者的 VoIP 路由](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users)原則。

#### <a name="routing-extension-numbers"></a>路由延伸模組號碼

為分支網站使用者準備撥號對應表和語音原則時，請務必包含符合 msRTCSIP 行 (或 Line URI) 屬性中所用字串和數位格式的正規化規則和轉譯規則，如此一來，在分支網站使用者與中央網站使用者之間啟用的商務用 Skype呼叫將會正確地路由傳送，特別是當呼叫必須透過 PSTN 重新路由傳送，因為 WAN 連結無法使用時。 此外，撥號號碼有特殊考慮，包括擴充號碼，而不只是電話號碼。

與包含擴充號碼的行 URI 相符的正規化規則和轉譯規則，不論是獨佔或完整 E.164 電話號碼，都有額外的需求。 本節描述數個範例案例，以路由傳送具有擴充號碼之 Line URI 的呼叫。

如果您的組織沒有直接向內撥號 (DID) 為個別使用者設定的電話號碼，而且每個使用者的 Line URI 都只設定一個擴充號碼，則內部使用者只要撥號即可彼此通話。 不過，您必須設定正規化規則，以套用至從分支網站使用者到中央網站使用者的呼叫，且該呼叫符合擴充號碼。

在分支網站與中央網站之間有 WAN 連結可用的案例中，從分支網站使用者到中央網站使用者的呼叫不需要比對正規化規則來轉譯號碼，因為呼叫不會透過 PSTN 路由傳送。 例如：

|**規則名稱**|**描述**|**號碼模式**|**轉換**|**範例**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |不轉譯 5 位數的數位  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 未翻譯  <br/> |

您也必須容納特定案例的擴充號碼，例如當分支月臺與中央月臺之間的 WAN 連結無法使用，而且必須透過 PSTN 路由傳送分支月臺的呼叫時。 在 WAN 中斷期間，如果分支網站使用者只透過撥打中央網站使用者的擴充功能來呼叫中央網站使用者，您必須有輸出轉譯規則，以新增中央網站使用者的完整電話號碼。 如果使用者的線路 URI 包含您組織的完整電話號碼和使用者的唯一擴充號碼，而不是使用者唯一的完整電話號碼，則您必須有輸出轉譯規則，改為新增組織的完整電話號碼。 例如：

|**說明**|**比對模式**|**轉換**|**範例**|
|:-----|:-----|:-----|:-----|
|將 5 位數的數位轉譯為使用者的電話號碼和擴充功能  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 會轉譯為 +14255550123;ext=10001  <br/> |
|將 5 位數號碼轉譯為組織的電話號碼和使用者的擴充功能  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 會轉譯為 +14255550100;ext=10001  <br/> |

在此案例中，如果處理重新路由傳送至 PSTN 的主幹對等互連不支援擴充號碼，則輸出轉譯規則也必須移除擴充號碼。 例如：

|**說明**|**比對模式**|**轉換**|**範例**|
|:-----|:-----|:-----|:-----|
|從具有擴充功能的電話號碼移除擴充功能  <br/> |^\+ (\d \*) ;ext= (\d \*) $  <br/> |+$1  <br/> |+14255550123;ext=10001 會轉譯為 +14255550123  <br/> |

不論 WAN 連結是否可用，如果您的組織沒有為個別使用者設定 DID 號碼，且使用者的線路 URI 包含您組織的電話號碼和使用者的唯一擴充號碼，則您必須設定組織的電話號碼線路 URI，其號碼可由分支網站的主幹對等或 PSTN 閘道連線。 您也必須設定組織的電話號碼線路 URI，以包含自己的唯一擴充功能，以便將通話路由傳送至該號碼。

#### <a name="preparing-for-voice-mail-survivability"></a>準備語音信箱擴充性

Exchange整合通訊 (UM) 通常只會安裝在中央網站，而不是在分支月臺上。 即使分支網站與中央網站之間的 WAN 連結無法使用，呼叫端也應該能夠留下語音信箱訊息。 因此，除了適用于該語音信箱號碼的語音原則、撥號對應表和正規化規則以外，為分支網站使用者提供語音信箱的Exchange UM 自動語音應答電話號碼設定行 URI 需要特殊考慮。

Survivable Branch Appliance (SBA) 和 Survivable Branch Servers 可在 WAN 中斷期間為分支使用者提供語音信箱生存能力。 具體而言，如果您使用 Survivable Branch Appliance 或 Survivable Branch Server，且 WAN 變得無法使用，則 SBA 或 Survivable Branch Server 會透過 PSTN 重新路由傳送未接聽的呼叫，以在中央網站Exchange UM。 透過 SBA 或 Survivable Branch Server，使用者也可以在 WAN 中斷期間透過 PSTN 擷取語音信箱訊息。 最後，在 WAN 中斷期間，Survivable Branch Appliance 或 Survivable Branch Server 會將未接來電通知排入佇列，然後在 WAN 還原時將其上傳至 Exchange UM 伺服器。 為了協助確保語音信箱重新路由具有復原性，請務必將中央網站集區的 FQDN 專案和 Edge Server FQDN 的專案新增至 Survivable Branch Server 上的主機檔案。 否則，如果您在分支月臺上沒有 DNS 伺服器，DNS 解析可能會逾時。

針對分支網站使用者的語音信箱生存能力，我們建議使用下列設定：

- Microsoft Exchange 系統管理員應該將 Exchange UM 自動語音應答 (AA) 設定為只接受訊息。 此設定會停用所有其他泛型功能，例如傳送至使用者或傳送至操作員，並將 AA 限制為只接受訊息。 或者，Exchange系統管理員可以使用一般 AA 或自訂的 AA，將呼叫路由傳送至操作員。

- 商務用 Skype Server系統管理員應該採用 AA 電話號碼，並在 Survivable Branch Appliance 或分支伺服器的語音信箱重新路由設定中，使用該電話號碼作為 **交換 um 自動語音應答** 號碼。

- 商務用 Skype Server系統管理員應該取得Exchange UM 訂閱者存取電話號碼，並在 Survivable Branch Server 或 Survivable Branch Server 的語音信箱重新路由設定中使用該號碼作為 **訂閱者存取** 號碼。

- 商務用 Skype Server系統管理員應該設定 Exchange UM，以便在 WAN 中斷期間，只有一個撥號對應表與所有需要存取語音信箱的分支使用者相關聯。

- 當 WAN 連結無法使用時，對分支網站使用者的通話可以路由傳送至使用者的Exchange整合通訊 (UM) 語音信箱，但前提是套用至通話的語音原則會指定唯一且不包含擴充號碼的語音信箱電話號碼。

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Branch-Site復原的硬體和軟體需求

硬體和軟體需求會根據您的復原解決方案而有所不同。

#### <a name="requirements-for-survivable-branch-appliances"></a>Survivable Branch Appliance 的需求

必要的硬體和軟體內建于 Survivable Branch Appliance 中。 不過，我們也建議每個分支月臺部署 DHCP 伺服器以取得用戶端 IP 位址;否則，當 DHCP 租用到期時，用戶端將不會有 IP 連線能力。

如果企業 DNS 伺服器只位於中央網站，分支月臺使用者將無法在 WAN 中斷期間連線到它們，因此商務用 Skype Server使用 DNS SRV (服務的探索 (SRV) 資源記錄) 將會失敗。 為了確保在 WAN 中斷期間提示重新路由，必須在分支月臺快取 DNS 記錄。 如果分支路由器支援，請開啟 DNS 快取。 或者，您可以在 分支部署 DNS 伺服器。 這可以是獨立伺服器或支援 DNS 功能的 Survivable Branch Appliance 版本。 如需詳細資訊，請連絡您的 Survivable Branch Appliance 提供者。

> [!NOTE]
> 在分支月臺上不需要有網域控制站。 Survivable Branch Appliance 會使用特殊憑證來驗證用戶端，該憑證會在用戶端登入時傳送用戶端以回應用戶端的憑證要求。

商務用 Skype用戶端可以使用 DHCP 選項 120 (SIP 註冊機構選項) 來探索商務用 Skype Server。 這可以透過下列兩種方式之一來設定：

- 在分支月臺設定 DHCP 伺服器以回復 DHCP 120 查詢，這會傳回 Survivable Branch Appliance 或 Survivable Branch Server 上註冊機構的 FQDN。

- 開啟 商務用 Skype Server DHCP。 開啟此功能時，商務用 Skype Server註冊機構會回應 DHCP 選項 120 查詢。 請注意，註冊機構不會回應 DHCP 選項 120 以外的任何 DHCP 查詢。

此外，對於具有多個子網的較大分支月臺，應啟用 DHCP 轉送代理程式，以將 DHCP 選項 120 查詢轉送至 DHCP 伺服器 (組態 1) 或註冊機構 (設定 2) 。

最後，分支網站使用者必須設定為企業語音，並使用適當的整合通訊端點進行布建。

#### <a name="requirements-for-survivable-branch-servers"></a>Survivable Branch Server 的需求

Survivable Branch Server 的需求與前端伺服器的需求相同。 如需詳細資訊，請[參閱 商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Full-Scale 商務用 Skype Server Branch-Site部署的需求

如需詳細資訊，請參閱規劃檔中的[商務用 Skype Server 2015 的伺服器](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)需求。

### <a name="example-configuring-a-failover-route"></a>範例：設定容錯移轉路由

 下列範例顯示系統管理員如何定義當 Dallas-GW1 因維修或其他緣故而無法使用時所要使用的容錯移轉路由。下表說明所需的設定變更。

**表 1. 使用者原則**

|**使用者原則**|**電話使用方式**|
|:-----|:-----|
|預設通話原則  <br/> |本機  <br/> GlobalPSTNHopoff  <br/> |
|Redmond 本地原則  <br/> |RedmondLocal  <br/> |
|Dallas 通話原則  <br/> |達拉斯使用者  <br/> GlobalPSTNHopoff  <br/> |

**表 2. 路由**


| **路由名稱**             | **號碼模式** | **電話使用方式**         | **樹幹**                                 | **閘道**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Redmond 本地路由  <br/> | ^\+1 (425           | 206                     | 253)  (\d {7}) $  <br/>                       | 本機  <br/> RedmondLocal  <br/>                |
| Dallas 本地路由  <br/>  | ^\+1 (972           | 214                     | 469)  (\d {7}) $  <br/>                       | 本機  <br/>                                    |
| 全域路由  <br/>     | ^\+？ (\d \*) $  <br/> | GlobalPSTNHopoff  <br/> | 主幹1  <br/> 主幹2  <br/> 主幹3  <br/> | Red-GW1  <br/> Red-GW2  <br/> 達拉斯-GW1  <br/> |
| Dallas 使用者路由  <br/>  | ^\+？ (\d \*) $  <br/> | 達拉斯使用者  <br/>      | 主幹3  <br/>                             | 達拉斯-GW1  <br/>                               |

表 1 中，在「Dallas 通話原則」的「DallasUsers」電話使用方式後，將新增 GlobalPSTNHopoff 電話使用方式。如此可讓具有「Dallas 通話原則」的電話在無法使用 DallasUsers 電話使用方式的路由時，可以使用為 GlobalPSTNHopoff 電話使用方式所設定的路由。