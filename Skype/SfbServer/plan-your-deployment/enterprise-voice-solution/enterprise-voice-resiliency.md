---
title: 在商務用 Skype Server 中規劃企業語音恢復功能
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
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: 瞭解如何在中央網站和分支網站商務用 Skype Server 企業語音中支援語音彈性。 分支網站選項包括部署 Survivable 分支裝置或 Survivable Branch Server。
ms.openlocfilehash: ec0d542318023fdc638926e78ff6ffdeceefba5f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778003"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃企業語音恢復功能

瞭解如何在中央網站和分支網站商務用 Skype Server 企業語音中支援語音彈性。 分支網站選項包括部署 Survivable 分支裝置或 Survivable Branch Server。

語音恢復指的是，如果主控商務用 Skype Server 的中央網站無法使用（不論是透過廣域網路絡 (WAN) 失敗或其他原因），則使用者可以繼續撥打和接聽電話的能力。 若中央網站失敗，企業語音服務必須透過無縫容錯移轉至備份網站而繼續中斷。 在 WAN 失敗的情況下，必須將分支網站來電重新導向至本機 PSTN 閘道。 本節討論在中央網站或 WAN 失敗的情況時，如何規劃語音彈性。

## <a name="central-site-resiliency"></a>中央網站恢復能力

越來越多的企業開始將網站散佈到全球各地。 維護緊急服務、存取服務台，以及在中央網站停止服務時執行重要商務工作的能力，對任何企業語音恢復解決方案而言都是必要的。 當中央網站無法使用時，必須符合下列條件：

- 必須提供語音容錯移轉功能。

- 一般在中央網站上使用前端集區註冊的使用者，必須能夠使用替代的前端集區註冊。 若要執行此動作，可以建立多個 DNS SRV 記錄，每個記錄會解析為每一個中央網站的 Director 集區或前端集區。 您可以調整 SRV 記錄的優先順序和權重，這樣該中央網站所提供的使用者就能在其他 SRV 記錄中取得對應的 Director 和前端集區。

- 撥入其他網站或由其他網站撥出的使用者通話必須重新路由至 PSTN。

本主題說明保障中央網站語音恢復能力的建議解決方案。

### <a name="architecture-and-topology"></a>架構與拓撲

在中央網站規劃語音彈性功能時，需要對商務用 Skype Server 註冊機構在啟用語音容錯移轉中所扮演的中央角色有基本瞭解。 商務用 Skype Server 註冊機構是一種服務，可讓用戶端註冊及驗證，並提供路由服務。 它會在所有的 Standard Edition server、前端伺服器、Director 或 Survivable 分支裝置上執行。 註冊集區包含在前端集區上執行的註冊機構服務，且位於相同的網站。 商務用 Skype 用戶端會透過下列探索機制來探索前端集區：

1. DNS SRV 記錄

2. 自動探索 Web 服務

3. DHCP 選項 120

商務用 Skype 用戶端連接至前端集區之後，它會由負載平衡器導向集區中的前端伺服器之一。 然後，該前端伺服器又會將用戶端重新導向至集區中的首選註冊機構。

每個為企業語音啟用的使用者會指派給特定的註冊機構集區，該集區會變成該使用者的主要註冊集區。 在特定網站上，數百名或數千名使用者通常會共用單一主要登錄器集區。 為了針對任何一個分支網站裡倚賴中央網站以獲得顯示狀態、會議或容錯移轉功能的使用者，記錄其對中央網站資源的使用情況，建議您將每位分支網站使用者視為向中央網站註冊的使用者。 分支網站使用者數目（包括註冊 Survivable Branch 裝置的使用者）目前沒有任何限制。

為了確保中央網站故障時的語音恢復能力，主要登錄器集區必須在另一個網站上設有一台指定的備份登錄器集區。 您可以使用拓撲產生器恢復設定來設定備份。 假設兩個網站之間存在可恢復的 WAN 連結，則已無法再使用主要登錄器集區的使用者會自動導向至備用登錄器集區。

下列步驟說明用戶端探索與註冊程序：

1. 用戶端透過 DNS SRV 記錄探索商務用 Skype Server。 在商務用 Skype Server 中，可以將 dns srv 記錄設定為將多個 FQDN 傳回 DNS srv 查詢。 例如，如果 Contoso 企業擁有三個中央網站 (北美、歐洲與亞太地區) 並在每個中央網站擁有一個 Director 集區，DNS SRV 記錄可以分別指向這三個位置的個別 Director 集區 FQDN。 只要其中一個位置有 Director 集區可用，用戶端可以連線至第一個躍點商務用 Skype Server。

    > [!NOTE]
    > 使用 Director 集區是選用的。 可以改為使用前端集區。

2. Director 集區會將使用者的主要註冊區集區和備份註冊區集區告知商務用 Skype 用戶端。

3. 商務用 Skype 用戶端會先嘗試連接至使用者的主要註冊集區。 如果主要登錄器集區有回應，該登錄器就會接受註冊。 如果無法使用主要註冊集區，商務用 Skype 用戶端會嘗試連線至備份註冊機構集區。 如果備份報名者集區可供使用，且已決定使用者的主要註冊集區無法使用 (請偵測指定的容錯移轉間隔不足的偵測) 。備份註冊器集區會接受使用者的註冊。 在備份註冊機構偵測到主要報名者再次可用之後，[備份註冊機集區] 會將容錯移轉用戶端重新導向至其主要集區。

### <a name="requirements-and-recommendations"></a>需求和建議

以下為大多數組織在實作中央網站語音恢復能力時適用的需求與建議事項：

- 主要與備份登錄器集區所屬網站必須由可恢復的 WAN 連結來串連。

- 每個中央網站必須內含一個登錄器集區，且該集區必須包含一或多個登錄器。

- 每個註冊機構集區都必須使用 DNS 負載平衡、硬體負載平衡或兩者兩者進行負載平衡。 如需規劃負載平衡設定的詳細資訊，請參閱[商務用 Skype 的負載平衡需求](../../plan-your-deployment/network-requirements/load-balancing.md)。

- 每個使用者都必須使用商務用 Skype Server 管理命令介面 **get-csuser 指令程式**，或商務用 Skype Server 控制台，指派給主要註冊集區。

- 主要登錄器集區必須在其他中央網站設有一個備份登錄器集區。

- 主要登錄器集區必須設為容錯移轉至備份登錄器集區。 主要登錄器集區預設會在故障超過 300 秒之後容錯移轉至備份登錄器集區。 您可以使用商務用 Skype Server 拓撲產生器來變更此間隔。

- 設定容錯移轉路由。 設定路由時，所指定的閘道必須與主要路由之指定閘道分屬不同網站。

- 若中央網站包含您的主要管理伺服器，且該網站可能長時間關機，您需要在備份網站重新安裝管理工具;否則，您將無法變更任何管理設定。

### <a name="dependencies"></a>相依性

商務用 Skype Server 取決於下列基礎結構和軟體元件，以確保語音復原能力：

|**元件** <br/> |**功能** <br/> |
|:-----|:-----|
|DNS  <br/> |負責解析 SRV 記錄與 A 記錄以因應伺服器對伺服器，及伺服器對用戶端的連線需求  <br/> |
|Exchange 與 Exchange Web 服務 (EWS)  <br/> |連絡儲存裝置；行事曆資料  <br/> |
|Exchange 整合通訊與 Exchange Web 服務  <br/> |通話記錄、語音信箱清單、語音信箱  <br/> |
|DHCP 選項 120  <br/> |如果無可用的 DNS SRV，用戶端會嘗試使用 DHCP 選項 120 來探索登錄器。 若要執行此作業，必須設定 dhcp 伺服器或啟用商務用 Skype Server dhcp。  <br/> |

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

  - 設定每一位使用者的 Exchange UM 撥號對應表，以在中央網站和備份網站上同時包括 Exchange um 伺服器，但將備份 Exchange UM 伺服器指定為已停用。 若主網站無法使用，Exchange 管理員必須將備份網站上的 Exchange UM 伺服器標示為 [已啟用]。

    如果上述兩種解決方案皆無法使用，則當中央網站無法使用時，就無法使用 Exchange UM。

- 所有會議類型

    已經容錯移轉至備份網站的使用者，可以加入由開放使用集區的召集人所建立或主控的會議，但是由於該使用者所屬的主要集區已經不再提供服務，因此無法自行建立或主控會議。 同樣地，其他使用者無法加入位於受影響使用者之主要集區上的會議。

下列語音功能在主要中央網站中斷服務時將無法運作：

- 會議自動語音應答

- 顯示狀態與 DND 基礎路由

- 更新來電轉接設定

- 回應群組服務和通話駐留

- 佈建新電話與用戶端

- 通訊錄 Web 搜尋

## <a name="branch-site-resiliency"></a>分支網站恢復功能

如果您想要提供分支網站恢復能力，也就是高可用性的企業語音服務，您有三個選項可供您執行：

- Survivable Branch Appliance

- Survivable Branch Server

- 分支網站上的完整商務用 Skype Server 部署

此指南會協助您評估最適合您組織的恢復能力解決方案，以及根據恢復能力解決方案，評估要使用的 PSTN 連線解決方案。也會協助您說明先決條件及其他規劃考量，以準備部署選擇的解決方案。

### <a name="branch-site-resiliency-features"></a>分支網站恢復功能

如果您提供分支網站恢復能力，當分支網站與中央網站的 WAN 連線失敗，或是無法存取中央網站時，下列語音功能應該仍然可用：

- 輸入和輸出公用交換電話網路 (PSTN) 通話

- 相同與不同的網站之間的使用者，皆可進行企業通話

- 基本通話處理，包括通話保留、取回和轉接

- 兩方立即訊息

- 來電轉接、端點同時響鈴、呼叫委派及小組通話服務，但只有在 delegator 和代理人 (例如，管理員和管理員的系統管理員) 或所有小組成員，都是在相同的網站上設定

- Cdr)  (詳細通話記錄

- 使用會議自動語音應答的 PSTN 電話撥入式會議

- 語音信箱功能（如果您設定語音信箱重新路由設定）。

- 使用者驗證和授權

下列功能只有在您的恢復解決方案是在分支網站上進行大規模商務用 Skype Server 部署時才會使用：

- IM、web 及 A/V 會議

- 目前狀態和請勿打擾 (DND) 型路由 (禁止通話在已啟用 DND 的分機上響鈴) 

- 更新來電轉接設定

- 回應群組應用程式和通話駐留應用程式

- 布建新的電話和用戶端，但只有在分支網站有 Active Directory 網域服務。

- 增強型 9-1-1 (E9-1-1) 

    如果已部署 E9-1-1，而中央網站的 SIP 主幹無法使用，因為 WAN 連結已關機，則 Survivable Branch 裝置會將 E9-1-1 呼叫路由傳送至本機分支閘道。 若要啟用此功能，分支網站使用者的語音原則應該會在發生 WAN 失敗時，將通話路由傳送至本地閘道。

> [!NOTE]
> SBA (survivable branch office) 不支援 XMPP。 位於 SBA 設定中的使用者將無法使用 XMPP 連絡人傳送 IMs 或查看顯示狀態。

### <a name="branch-site-resiliency-solutions"></a>分支網站恢復解決方案

為您的組織提供分支網站恢復能力的好處是顯而易見的。 具體而言，如果您失去中央網站的連線，分支網站使用者將會繼續企業語音服務和語音信箱 (如果您設定) 的語音信箱重新路由設定。 但對於使用者人數低於 25 位的網站而言，恢復能力解決方案所提供的投資報酬率可能不夠。

如果您決定要提供分支網站恢復能力，您有三個選項。下表可協助您判斷最適合您的組織之選項。

|**如果您...**|**建議您使用...**|
|:-----|:-----|
|在您的分支網站上主控 25 到 1000 名使用者，且投資報酬率不足以支應完整部署，或是不具本機管理支援  <br/> |Survivable Branch Appliance  <br/> Survivable 分支裝置是業界標準的刀片式伺服器，具有在 Windows server 2008 R2 上執行的商務用 Skype Server 註冊裝置和轉送伺服器。 Survivable Branch 裝置也包含公用交換電話網路 (PSTN) 閘道。 合格的第三方裝置 (由參與 Survivable Branch Appliance (SBA) 資格/認證方案的 Microsoft 協力廠商所開發) 在 WAN 失效時仍可提供持續的 PSTN 連線，但這個方法無法提供可恢復的顯示狀態與會議功能，因為這些功能依存於中央網站上的前端伺服器。  <br/> 如需 Survivable 分支裝置的詳細資訊，請參閱本主題稍後的「Survivable Branch 裝置詳細資料」。  <br/> **附注：** 如果您決定同時將 SIP 主幹與 Survivable 分支裝置搭配使用，請與您的 Survivable 分支裝置廠商聯繫，以瞭解哪一種服務提供者最適合您的組織。 <br/> |
|在分支網站上的1000和2000使用者間主機、缺乏彈性的 WAN 連線，且有訓練有素的商務用 Skype Server 系統管理員可用  <br/> |Survivable 分支伺服器或兩個 Survivable 分支裝置。  <br/> Survivable 分支伺服器是 Windows 伺服器會議：指定的硬體需求，其上已安裝商務用 Skype Server 註冊機構和轉送伺服器軟體。 該伺服器必須將 PSTN 閘道或 SIP 主幹連線至電話服務提供者。  <br/> 如需 Survivable 分支伺服器的詳細資訊，請參閱本主題稍後的「Survivable Branch Server Details。」。  <br/> |
|如果您需要最多5000使用者的語音功能，且有訓練有素的商務用 Skype Server 系統管理員可用，請使用目前狀態和會議功能。  <br/> |以 Standard Edition Server 部署為中央網站，而非分支網站。  <br/> 在發生 WAN 失敗時，完整的商務用 Skype Server 部署可提供連續的 PSTN 連線和彈性顯示功能和會議。  <br/> |

#### <a name="resiliency-topologies"></a>恢復能力拓撲

下圖顯示分支網站恢復能力所適用的建議拓撲。

**分支網站恢復能力選項**

![語音分支恢復選項。](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance 詳細資料

商務用 Skype Server Survivable Branch 裝置包含下列元件：

- 使用者驗證、登錄與通話路由所需的登錄器

- 用以處理登錄器與 PSTN 閘道間往來訊號的中繼伺服器

- 在 WAN 中斷時，用以將通話路由至 PSTN 作為後援傳輸的 PSTN 閘道

- 供本機使用者存放資料的 SQL Server Express

Survivable 分支裝置也包含 PSTN 主幹、類比埠和乙太網路介面卡。

如果分支網站與中央網站之間的 WAN 連線無法使用，則內部分支使用者仍會向 Survivable Branch 裝置註冊機構註冊，並使用 Survivable Branch 裝置連接至 PSTN，以取得不間斷的語音服務。 當分支網站的 WAN 連結無法使用時，從家中或其他遠端位置連線的分支網站使用者將可使用中央網站上的登錄器伺服器進行登錄。 這些使用者將可擁有完整的整合通訊功能，但有一例外，傳入分支網站的來電會轉接至語音信箱。 當 WAN 連線恢復時，分支網站使用者即應可重獲完整的功能。 容錯移轉至 Survivable Branch 裝置或服務的還原，都不需要有 IT 系統管理員的狀態。

商務用 Skype Server 在分支網站上支援最多兩個 Survivable 分支裝置。

#### <a name="survivable-branch-appliance-deployment-overview"></a>Survivable Branch Appliance 部署概觀

Survivable 分支裝置是由原始設備製造商生產，與 Microsoft 合作，並由增值零售商自行部署。 只有在中央網站部署商務用 Skype Server 後，才會發生此部署，分支網站的 WAN 連線已到位，且已啟用分支網站使用者的企業語音。

如需這些階段的詳細資訊，請參閱部署文件中的＜[Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server)＞。

|**階段**|**步驟**|**使用者權限**|
|:-----|:-----|:-----|
|為 Survivable Branch 裝置設定 Active Directory 網域服務  <br/> |**在中央網站上：** <br/>  在分支網站上，為將安裝及啟動 Survivable 分支裝置的技術人員建立網域使用者帳戶 (或企業身分識別) 。 <br/>  使用 Active Directory 網域服務中 Survivable Branch 裝置的適用的完整功能變數名稱 (FQDN) ) ，建立電腦帳戶 (。 <br/>  在 [拓撲產生器] 中，建立併發布 Survivable Branch 裝置。 <br/> |技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。 Survivable 分支裝置必須屬於 RTCSBAUniversalServices 群組，這會在您使用拓撲產生器時自動進行。  <br/> |
|安裝和啟動 Survivable 分支裝置。  <br/> |**在分支網站上：** <br/>  將 Survivable 分支裝置連線至乙太網路埠和 PSTN 埠。 <br/>  啟動 Survivable 分支裝置。 <br/>  使用在中央網站為 Survivable Branch 裝置建立的網域使用者帳戶，將 Survivable 分支裝置加入網域。 設定 FQDN 與 IP 位址，使其符合在電腦帳戶中建立的 FQDN。 <br/>  使用 OEM 使用者介面設定 Survivable 分支裝置。 <br/>  測試 PSTN 連線。 <br/> |技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。  <br/> |

#### <a name="survivable-branch-server-details"></a>Survivable Branch Server 詳細資料

在 [拓撲產生器] 中，建立分支網站，將 Survivable 分支伺服器新增至該網站，然後在您要安裝該角色的電腦上執行商務用 Skype Server 部署嚮導。

### <a name="branch-site-resiliency-requirements"></a>分支網站恢復需求

本主題將協助您為使用者準備分支網站恢復功能及語音信箱留存性，也會指定相關的硬體和軟體需求。

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>準備分支使用者 Branch-Site 恢復功能

將其註冊機構集區設為 Survivable Branch 裝置 (SBA) 或 Survivable Branch Server），為使用者準備分支網站恢復功能。

#### <a name="registrar-assignments-for-branch-users"></a>分支使用者的註冊機構指派

不論您選擇哪一個分支網站恢復解決方案，您都必須將主要註冊器指派給每個使用者。 分支網站使用者應始終向分支網站上的註冊機構註冊，不論該報名者是位於 Survivable branch 裝置、Survivable branch Server，還是獨立商務用 Skype Server Standard 或 Enterprise Edition 伺服器上。 網域名稱系統 (DNS) 服務 (SRV) 資源記錄是必要的，讓用戶端能夠探索其註冊區集區。 如果 Survivable 分支裝置無法使用，這就是分支網站用戶端將如何自動探索備份註冊機。

如果分支網站沒有 DNS 伺服器，有兩種方法可用於設定 Survivable 分支裝置或 Survivable Branch 伺服器的探索：

- 在分支網站的動態主機設定通訊協定上，設定 DHCP 選項120。 (DHCP) 伺服器指向 Survivable Branch 裝置或 Survivable Branch 伺服器的完整功能變數名稱 (FQDN) 。

- 設定 Survivable 分支裝置或 Survivable 分支伺服器以回應 DHCP 120 查詢。

#### <a name="voice-routing-for-branch-users"></a>分支使用者的語音路由

建議您建立個別的使用者層級語音 over 網際網路通訊協定 (VoIP 分支網站中使用者的) 原則。 這個原則應包含使用 Survivable Branch 裝置或 Branch server 閘道的主要路由，以及一個或多個在中央網站上使用具有公用電話 (交換網之公用電話) 閘道的主幹的備份路由。 如果主要路由無法使用，則改為使用使用一或多部中央網站閘道的備份路由。 這種方式不論登錄使用者的位置為何（位於中央網站的分支網站註冊機構或備份註冊機構集區），使用者的 VoIP 原則都是有效的。 這是容錯移轉案例的重要考慮。 例如，如果您需要重新命名 Survivable 分支裝置，或重新設定 Survivable Branch 裝置以連線至中央網站的備份註冊機構集區，則必須將分支網站使用者移至中央網站的持續時間。  (如需重新命名或重新配置 Survivable 分支裝置的詳細資訊，請參閱部署檔中的 [附錄 B：管理 Survivable Branch 裝置](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) 。 ) 如果這些使用者沒有使用者層級 VoIP 原則或使用者層級撥號對應表，當使用者移至另一個網站時，網站層級 VoIP 原則及網站層級撥號對應表的中央網站預設會套用至使用者。 而不是分支網站網站層級 VoIP 原則和撥號對應表。 在此情況下，除非備份註冊機構集區所使用的網站層級 VoIP 原則和網站層級撥號對應表也可以套用至分支網站使用者，否則他們的呼叫將會失敗。 例如，如果位於日本的分支網站中的使用者已移至 Redmond 中的中央網站，則在其上預置 + 1425 至所有7位數通話的正規化規則的撥號對應表，將不會適當地為這些使用者轉譯來電。

> [!IMPORTANT]
> 當您建立分支辦公室備份路由時，建議您將兩個 PSTN 電話使用方式記錄新增至分支 office 使用者原則，並將個別的路由指派給每個。 第一個或 [主要] 路由會直接呼叫與 Survivable Branch 裝置相關聯的閘道 (SBA) 或分支伺服器;第二個或 [備份] 路由會將呼叫直接呼叫至中央網站的閘道。 在接聽來電中，SBA 或 branch 伺服器會先嘗試所有指派給第一個 PSTN 使用方式記錄的路由，再嘗試第二個使用方式記錄。

為了協助確保當分支閘道或 Survivable 分支裝置網站的 Windows 元件無法使用時，對分支網站使用者的撥入呼叫會到達這些使用者 (這種情況會發生，例如，如果 Survivable branch 裝置或分支閘道已停機進行維護) ，請在閘道上建立容錯移轉路由 (或使用直接向內撥號 () 提供者) 重新導向來電至中央網站上的備份註冊機構集區。 在此，來電會透過 WAN 連結路由傳送至分支使用者。 請確定路由會轉譯數位，使其符合 PSTN 閘道或其他主幹對等公認的電話號碼格式。 如需建立容錯移轉路由的詳細資訊，請參閱設定 [容錯移轉路由](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route)。 另外，也為分支網站上與閘道相關聯的主幹建立服務層級撥號對應表，以正常化來電。 如果您有兩個 Survivable 分支裝置在分支網站上，您可以為這兩種方案建立一個網站層級撥號對應表，除非每個必要都要有個別的服務層級計畫。

> [!NOTE]
> 若要使用依賴中央網站以進行顯示狀態、會議或容錯移轉的任何分支網站使用者，針對中央網站資源的消費，建議您考慮每個分支網站使用者，就像使用者已向中央網站註冊。 分支網站使用者數目（包括註冊 Survivable Branch 裝置的使用者）目前沒有任何限制。

此外，我們也建議您建立使用者層級撥號對應表和語音原則，然後將其指派給分支網站使用者。 如需詳細資訊，請參閱在部署檔中建立[或修改商務用 Skype Server 的撥號](../../deploy/deploy-enterprise-voice/dial-plans.md)對應表，並[為分支使用者建立 VoIP 路由原則](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users)。

#### <a name="routing-extension-numbers"></a>路由分機號碼

為分支網站使用者準備撥號對應表和語音原則時，請務必包含符合 msRTCSIP-line (或 line URI) 屬性中所用之字串及數位格式的正規化規則和轉譯規則，如此一來，在分支網站使用者與中央網站使用者之間啟用商務用 Skype 呼叫會正確地路由，尤其是當必須透過 WAN 連結無法使用時，必須以 PSTN 重新路由傳送。 此外，撥打號碼的特殊考慮（包括分機號碼），而不只是電話號碼。

包含分機號碼之行 URIs 的正規化規則和轉譯規則，不論是獨佔還是除了完整的 e.164 電話號碼，都有額外的需求。 本節說明使用分機號碼來路由傳送電話 URIs 的幾個範例案例。

如果您的組織沒有直接向內撥號 () 為個別使用者設定的電話號碼，且每位使用者的線路 URI 只會以分機號碼來設定，則內部使用者可以只撥打分機號碼撥打一個分機號碼。 不過，您必須設定標準化規則，以套用至分支網站使用者的呼叫與分機號碼相符的中央網站使用者。

在分支網站與中央網站之間的 WAN 連結可供使用的情況下，分支網站使用者對中央網站使用者的呼叫不需要符合的正規化規則來轉譯號碼，因為通話不會透過 PSTN 路由傳送。 例如：

|**規則名稱**|**描述**|**號碼模式**|**轉換**|**範例**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |不轉譯5位數的數位  <br/> |^(\d{5})$  <br/> |$1  <br/> |未轉譯10001  <br/> |

您也必須在特定案例中容納分機號碼，例如在分支網站與中央網站之間的 WAN 連結無法使用，以及必須透過 PSTN 路由傳送分支網站的電話時。 在 WAN 中斷期間，如果分支網站使用者只會撥打中央網站使用者的分機呼叫中央網站使用者，您必須有一個輸出轉譯規則，以加入中央網站使用者的完整電話號碼。 如果使用者的列 URI 包含您組織的完整電話號碼和使用者的唯一分機號碼，而不是使用者特有的完整電話號碼，則您必須有一個輸出轉譯規則，可改為新增組織的完整電話號碼。 例如：

|**描述**|**符合模式**|**轉換**|**範例**|
|:-----|:-----|:-----|:-----|
|將5位數號碼轉譯為使用者的電話號碼和分機號碼  <br/> |^(\d{5})$  <br/> |+ 14255550123; ext = $ 1  <br/> |10001會轉譯為 + 14255550123; ext = 10001  <br/> |
|將5位數號碼轉譯為您組織的電話號碼和使用者的分機號碼  <br/> |^(\d{5})$  <br/> |+ 14255550100; ext = $ 1  <br/> |10001會轉譯為 + 14255550100; ext = 10001  <br/> |

在此案例中，如果處理與 PSTN 間重新路由的主幹對等動作不支援分機號碼，則輸出轉譯規則也必須移除分機號碼。 例如：

|**描述**|**符合模式**|**轉換**|**範例**|
|:-----|:-----|:-----|:-----|
|從具有分機號碼的電話號碼中移除分機號碼  <br/> |^\+ ( \d \*) ; ext = ( \d \*) $  <br/> |+ $1  <br/> |+ 14255550123; ext = 10001 會轉譯成 + 14255550123  <br/> |

WAN 連結是否可供使用時，如果您的組織未針對個別使用者設定號碼，且使用者的線路 URI 中包含組織的電話號碼和使用者的唯一分機號碼，則您必須使用分支網站上的主幹對等或 PSTN 閘道可存取的號碼，設定組織的電話號碼行 URI。 您也必須設定組織的電話號碼行 URI，以包含其專屬的唯一分機，以路由傳送至該號碼。

#### <a name="preparing-for-voice-mail-survivability"></a>準備語音信箱留存能力

Exchange整合通訊 (UM) 通常只安裝在中央網站，而非位於分支網站。 即使分支網站與中央網站之間的 WAN 連結無法使用，來電者還是可以留下語音信箱訊息。 因此，設定 Exchange UM 自動語音應答電話號碼的行 URI，為分支網站使用者提供語音信箱時，除了語音原則、撥號對應表，以及適用于該語音信箱號碼的正規化規則之外，還需要特別考慮。

Survivable 分支裝置 (Sba) 和 Survivable 分支伺服器在 WAN 中斷期間為分支使用者提供語音信箱留存能力。 具體說來，如果您是使用 Survivable 分支裝置或 Survivable 分支伺服器，而 WAN 變成無法使用，則 SBA 或 Survivable branch 伺服器會透過 PSTN 將未接聽的呼叫重新連接至中央網站的 Exchange UM。 透過 SBA 或 Survivable Branch 伺服器，使用者也可以透過 PSTN 在 WAN 中斷期間取回語音信箱訊息。 最後，在 wan 中斷期間，Survivable Branch 裝置或 Survivable branch 伺服器會將未接來電通知排入佇列，然後在還原 wan 時將其上傳至 Exchange UM 伺服器。 若要協助確保語音信箱重新路由可復原，請確定您已將中央網站集區的 FQDN 和 Edge Server FQDN 專案的專案新增至 Survivable 分支伺服器上的主機檔案。 否則，如果您在分支網站上沒有 DNS 伺服器，則 DNS 解析可能會超時。

我們建議分支網站使用者的語音信箱留存能力的下列設定：

- Microsoft Exchange 管理員應該設定 Exchange UM 自動語音應答 (AA) 以只接受郵件。 此設定會停用所有其他一般功能，例如轉接至使用者或轉接至操作員，並且限制 AA 只接受郵件。 此外，Exchange 管理員也可以使用一般 AA 或自訂的 aa，將通話路由傳送至運算子。

- 商務用 Skype Server 管理員應該取得 AA 電話號碼，並使用該電話號碼做為 Survivable 分支裝置或分支伺服器之語音信箱重新路由設定中的 **exchange um 自動** 語音應答號碼。

- 商務用 Skype Server 管理員應該取得 Exchange UM 訂戶存取電話號碼，並使用該號碼做為 Survivable Branch 裝置或 Survivable branch 伺服器之語音信箱重新路由設定中的 **訂戶訪問** 號碼。

- 商務用 Skype Server 管理員應該設定 Exchange UM，這樣就只有一個撥號對應表與所有需要存取語音信箱的 WAN 中斷期間的分支使用者相關聯。

- 當 WAN 連結無法使用時，可將分支網站使用者的通話路由傳送至使用者的 Exchange 整合通訊 (UM) 語音信箱，但只有在套用至通話的語音原則指定了唯一且不含分機號碼的語音信箱電話號碼時。

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Branch-Site 恢復功能的硬體和軟體需求

硬體和軟體需求會根據您的恢復解決方案而有所不同。

#### <a name="requirements-for-survivable-branch-appliances"></a>Survivable 分支裝置的需求

必要的硬體和軟體已內置於 Survivable 分支裝置中。 不過，我們也建議每個分支網站部署 DHCP 伺服器以取得用戶端 IP 位址;否則，當 DHCP 租用到期時，用戶端將不會有 IP 連線能力。

如果企業 DNS 伺服器僅位於中央網站，分支網站使用者將無法在 WAN 中斷期間與其連線，因此商務用 Skype Server 使用 DNS SRV (服務的探索 (SRV) 資源記錄) 會失敗。 為了確保 WAN 中斷期間的提示重新路由，必須在分支網站上快取 DNS 記錄。 如果分支路由器支援，請開啟 DNS 快取。 或者，您可以在分支部署 DNS 伺服器。 這可以是獨立的伺服器，也可以是支援 DNS 功能的 Survivable 分支裝置版本。 如需詳細資訊，請與您的 Survivable 分支裝置提供者聯繫。

> [!NOTE]
> 不需要有分支網站的網域控制站。 Survivable 分支裝置會使用特殊的憑證來驗證用戶端，以回應用戶端的憑證要求登入。

商務用 Skype 用戶端可以使用 DHCP 選項 120 (SIP 註冊器選項) 探索商務用 Skype Server。 這可以採用下列其中一種方式進行設定：

- 在分支網站上設定 DHCP 伺服器以回復 DHCP 120 查詢，傳回 Survivable Branch 裝置或 Survivable Branch Server 上之註冊機的 FQDN。

- 開啟商務用 Skype Server DHCP。 開啟此選項時，商務用 Skype Server 註冊機構會回應 DHCP 選項120查詢。 請注意，註冊機構不會回應 DHCP 選項120以外的任何 DHCP 查詢。

此外，針對具有多個子網的大型分支網站，應啟用 DHCP 轉送代理程式，以將 DHCP 選項120查詢轉寄至 DHCP 伺服器 (設定 1) 或註冊機 (設定 2) 。

最後，必須對分支網站使用者設定企業語音，並使用適當的整合通訊端點進行布建。

#### <a name="requirements-for-survivable-branch-servers"></a>Survivable 分支伺服器的需求

Survivable 分支伺服器的需求與前端伺服器的需求相同。 如需詳細資訊，請參閱[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Full-Scale 商務用 Skype Server Branch-Site 部署的需求

如需詳細資訊，請參閱規劃檔中的[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。

### <a name="example-configuring-a-failover-route"></a>範例：設定容錯移轉路由

 下列範例顯示系統管理員如何定義當 Dallas-GW1 因維修或其他緣故而無法使用時所要使用的容錯移轉路由。下表說明所需的設定變更。

**表 1. 使用者原則**

|**使用者原則**|**電話使用方式**|
|:-----|:-----|
|預設通話原則  <br/> |本機  <br/> GlobalPSTNHopoff  <br/> |
|Redmond 本地原則  <br/> |RedmondLocal  <br/> |
|Dallas 通話原則  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**表 2. 路由**


| **路由名稱**             | **號碼模式** | **電話使用方式**         | **樹幹**                                 | **閘道**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Redmond 本地路由  <br/> | ^\+1 (425           | 206                     | 253)  ( \d {7}) $  <br/>                       | 本機  <br/> RedmondLocal  <br/>                |
| Dallas 本地路由  <br/>  | ^\+1 (972           | 214                     | 469)  ( \d {7}) $  <br/>                       | 本機  <br/>                                    |
| 全域路由  <br/>     | ^\+？ ( \d \*) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> 達拉斯-GW1  <br/> |
| Dallas 使用者路由  <br/>  | ^\+？ ( \d \*) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | 達拉斯-GW1  <br/>                               |

表 1 中，在「Dallas 通話原則」的「DallasUsers」電話使用方式後，將新增 GlobalPSTNHopoff 電話使用方式。如此可讓具有「Dallas 通話原則」的電話在無法使用 DallasUsers 電話使用方式的路由時，可以使用為 GlobalPSTNHopoff 電話使用方式所設定的路由。