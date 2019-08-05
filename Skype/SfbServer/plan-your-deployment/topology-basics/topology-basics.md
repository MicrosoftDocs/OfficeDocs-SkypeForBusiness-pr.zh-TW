---
title: 商務用 Skype Server 的拓撲基礎
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '摘要: 選擇商務用 Skype Server 的拓撲。 瞭解商務用 Skype Server 的伺服器 collocation。'
ms.openlocfilehash: 00154c754292fd960942f0f0da7f95bb6b5b1c19
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/23/2019
ms.locfileid: "36194114"
---
# <a name="topology-basics-for-skype-for-business-server"></a>商務用 Skype Server 的拓撲基礎

**摘要:** 選擇您的商務用 Skype Server 拓撲。 瞭解商務用 Skype Server 的伺服器 collocation。

在準備任何其他專案之前, 您可能會想知道您正在規劃適用于商務用 Skype Server 部署的正確拓撲。 您首先需要決定的做法是, 如果您要使用內部部署的商務用 Skype Server, 或是在混合式部署中將此專案與商務用 Skype Server Online 部署結合。 不論是哪一種方式, 您都會想進一步瞭解, 因為我們將在這裡詳細說明內部部署的拓撲, 但是混合式詳細資料會記錄在各自的區段中。

您也可以在[商務用 Skype Server 的參考拓朴](reference-topologies.md)中查看一些範例拓撲。

## <a name="sites"></a>網站

在商務用 Skype Server 中, 您可以在網路上定義包含商務用 Skype 伺服器元件的網站。 網站是一組由高速、低延遲網路連接的電腦, 例如單一局域網 (LAN), 或由高速光纖光纖網路連接的兩個網路。 請注意, 商務用 Skype Server 網站是來自 Active Directory 網域服務網站和 Microsoft Exchange Server 網站的個別概念。 您的商務用 Skype Server 網站不需要對應至 Active Directory 網站。

商務用 Skype 伺服器支援內部部署一或多個網站, 可根據您的高可用性和位置需求來調整。

您的部署將至少有一個中心網站 (又稱為資料中心), 而您部署中的每個中心網站都將有一個標準版伺服器, 或至少有一個企業版頂層端池。 您可以在下列各項選項中查看差異:

- 標準版伺服器包括 collocated SQL Server Express 資料庫。

- 企業版前端池包括:

  - 一或多個前端伺服器 (理想情況下至少為三個), 最多可達12個。 需要對多個伺服器進行負載平衡。

  - 個別的後端伺服器。

您可以在此區段中深入瞭解各種伺服器角色。

除了您的中央網站之外, 您也可能會有一個或多個與您的中央網站相關聯的分支網站。 它們依賴于中心網站, 幾乎所有的功能, 因此它們的用途是什麼？

- Survivable 分支裝置, 它結合了公用的交換電話網絡 (PSTN) 閘道, 以及部分商務用 Skype Server 功能。

- Survivable [分支伺服器], 它是執行 Windows Server 且已安裝商務用 Skype Server 註冊機構和轉送伺服器軟體的伺服器。

- 獨立 PSTN 閘道 (不是 Survivable 分支裝置的一部分)。

- 獨立的中繼伺服器或獨立的中繼伺服器池 (如果您不想將此角色與 Survivable 分支裝置 collocate)。

## <a name="whats-in-a-skype-for-business-server-site"></a>商務用 Skype Server 網站有什麼功能？

若要深入瞭解更多相關資訊, 中央網站也可以有:

- 在同一個網域或不同網域中有多個前端池, 請記住, 在規劃中的所有前端伺服器以及該池的後端伺服器, 都必須在同一個網域中。

- 多個標準版伺服器。

- Office Web Apps Server, 與商務用 Skype Server 中的 Office Web Apps 搭配使用, 以共用和轉譯 PowerPoint 簡報。

- Edge 伺服器或 Edge 池 (在周邊網路中)。 如果您想要讓您的部署支援同盟夥伴、公用 IM 連線、可擴展的訊息和目前狀態通訊協定 (XMPP) 閘道, 以及遠端使用者存取權, 您需要進行部署。 如需詳細資訊, 請參閱 Edge 伺服器規劃檔。

- 持續聊天伺服器。 如果您想要讓使用者能夠參與多個在一段時間內持續的主題式交談, 這項功能很有用。 規劃持續聊天伺服器主題有更多的資訊。

- 監控程式. 用來支援音訊/視頻 (A/V) 體驗品質 (QoE) 的資料收集, 以及在您的部署中呼叫企業語音和 A/V 會議的詳細資料錄製 (CDR)。 我們將在規劃監視主題中詳細討論。

- 主管或主管池。 不需要, 但如果您想要改善復原能力, 並讓商務用 Skype 使用者要求重新導向至使用者的主區, 則此方法很有用。 如果您想要部署控制器, 每個池最多可支援10個。 如果這是您需要的專案, 請務必繼續閱讀規劃主管主題。

- 反向 proxy。 這不是商務用 Skype Server 元件, 但如果您想要支援同盟使用者的網頁內容共用, 如果您想要支援行動流量, 如果您的遠端使用者想要使用通訊錄、加入會議等, 這就是您要的問題。想要在您的環境中使用。 當您準備好時, 請參閱設定反向 proxy 伺服器主題, 以取得更多詳細資料。

以下提供這些伺服器之 collocation 的其他資訊。

部署在您中央網站的所有前端池和標準版伺服器, 假設您已部署下列各項:

||||
|:-----|:-----|:-----|
|主管或主管池  <br/> |獨立的中繼伺服器或轉送伺服器池  <br/> |Office Web Apps 伺服器  <br/> |
|Edge 伺服器或 Edge 池  <br/> |持續聊天伺服器或持久聊天伺服器池  <br/> |監控程式  <br/> |

此清單中的 Exchange 整合訊息 (UM) 伺服器在哪裡？ 當然, 如果您想要整合 Exchange UM, 但它不是商務用 Skype Server 網站的元件, 請務必將它與商務用 Skype Server 搭配使用, 因此我們不會在此提及。

您可能打算使用多個中央網站, 如果是這樣, 他們就可以共用下列伺服器和角色 (如果它們已部署在您的中央網站上):

|||
|:-----|:-----|
|獨立的中繼伺服器或轉送伺服器池  <br/> |Edge 伺服器或 Edge 池  <br/> |
|持續聊天伺服器或持久聊天伺服器池  <br/> |監控程式  <br/> |

就像最後一個清單一樣, 我們不會在這裡包含 Exchange UM 伺服器, 因為它不是商務用 Skype Server 部署的一部分, 但在這裡也會位於同一個類別中。

當然, 還有一些其他元件和選項可進入部署。

|||||
|:-----|:-----|:-----|:-----|
|道  <br/> |PSTN 閘道 (如果您部署企業語音  <br/> |Exchange UM 伺服器 (如果您想要與 Exchange UM 整合)  <br/> |DNS 負載平衡  <br/> |
|硬體負載平衡器  <br/> |SQL Server 資料庫  <br/> |檔案共用  <br/> ||

## <a name="server-roles"></a>伺服器角色

每個執行商務用 Skype 伺服器的伺服器都會執行一或多個伺服器角色。 伺服器角色是該伺服器所提供的一組商務用 Skype 伺服器功能。 您不需要在您的網路中部署所有可用的伺服器角色。 只安裝包含所需功能的伺服器角色。

針對大部分的伺服器角色, 如需可伸縮性和高可用性, 您可以將多個伺服器的 pool 部署在執行相同的伺服器角色。 池中的每個伺服器都必須執行相同的伺服器角色或角色。 針對商務用 Skype Server 中的大部分類型的 pool, 您必須部署負載平衡器, 以便在池中的各個伺服器之間散佈流量。 商務用 Skype 伺服器支援網域名稱系統 (DNS) 負載平衡與硬體負載平衡器。

### <a name="front-end-server-and-back-end-server"></a>前端伺服器和後端伺服器

在商務用 Skype Server Enterprise Edition 中, 前端伺服器是核心伺服器角色, 並執行許多基本的商務用 Skype 伺服器功能。 前端伺服器 (以及後端伺服器) 是任何商務用 Skype Server Enterprise Edition 部署所需的伺服器角色。

[前端] 池是一組前端伺服器 (配置相同), 共同作業為使用者群組提供服務。 多台執行相同角色的伺服器池提供可伸縮性和容錯移轉功能。

前端伺服器包括下列各項:

- 使用者驗證與註冊。

- 目前狀態資訊與連絡人卡片 exchange。

- 通訊錄服務與通訊群組清單展開。

- IM 功能, 包括多方 IM 會議。

- 網路會議、PSTN 電話撥入式會議及 A/V 會議 (如果已部署)。

- 針對商務用 Skype Server 隨附的兩個應用程式 (例如, 會議助理與回應群組應用程式) 和協力廠商應用程式的應用程式託管。

- 您也可以選擇監視, 以收集通話詳細資料記錄 (CDRs) 的使用方式資訊, 並呼叫錯誤記錄 (Cer)。 此資訊提供有關透過企業語音通話和 A/V 會議來遍歷您網路之媒體質量 (音訊與影片) 的統計資料。

- 網頁元件 (例如網頁排程程式及加入啟動器) 支援的 web 工作。

- 您可以選擇性地封存 IM 通訊與會議內容, 以符合合規性的原因。 如需詳細資訊, 請參閱規劃檔中的[存檔規劃](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)。

    在 Lync Server 2010 和早期版本中, 監視及封存是獨立的伺服器角色, 而不是在前端伺服器上 collocated。

- 您也可以選擇是否已啟用持續聊天、聊天室管理的持續聊天 Web 服務和檔案上傳/下載的持續聊天 Web 服務。

前端池也是使用者和會議資料的主要存儲區。 每個使用者的相關資訊會在池中的三個前端伺服器之間複製, 並在後端伺服器上備份。

此外, 部署中的一個前端伺服器也會執行中央管理伺服器, 該伺服器會將基本配置資料管理並部署到執行商務用 Skype Server 的所有伺服器。 中央管理伺服器也提供 Lync Server 管理命令介面和檔案傳輸功能。

後端伺服器是執行 Microsoft SQL Server 的資料庫伺服器, 可為前端池提供資料庫服務。 後端伺服器可做為池使用者與會議資料的備份儲存, 而且是其他資料庫 (例如回應群組資料庫) 的主要存儲區。 您可以使用單一後端伺服器, 但在進行容錯移轉時, 建議[在商務用 Skype server 中使用後端伺服器高可用性](../high-availability-and-disaster-recovery/back-end-server.md)。 後端伺服器不會執行任何商務用 Skype Server 軟體。

> [!IMPORTANT]
> 我們不建議將商務用 Skype Server 資料庫與其他資料庫 collocating。 如果您這麼做, 可用性和效能可能會受到影響。

> [!NOTE]
> 在商務用 Skype Server 2015 中提供 SQL 鏡像, 但商務用 Skype Server 2019 已不再支援。 使用商務用 Skype Server 2019 時, AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) 和 SQL 容錯移轉叢集方法都是可取的。

儲存在後端伺服器資料庫中的資訊包含目前狀態資訊、使用者的連絡人清單、會議資料, 包括所有目前會議狀態的永久性資料, 以及會議排程資料。

### <a name="edge-server"></a>Edge 伺服器

Edge 伺服器可讓您的使用者與組織防火牆以外的使用者進行通訊及共同作業。 這些外部使用者可以包含組織自己的使用者, 這些使用者目前正在異地作業、同盟夥伴組織的使用者, 以及受邀加入在您的商務用 Skype Server 部署中舉行會議的外部使用者。

部署 Edge 伺服器也會啟用行動裝置服務, 支援行動裝置上的 Lync 功能。 使用者可以使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置來執行諸如傳送和接收立即訊息、查看連絡人及查看目前狀態等活動。 此外, 行動裝置支援一些企業語音功能, 例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電。 行動裝置功能也支援不支援在背景中執行之應用程式之行動裝置的推播通知。 推播通知是傳送給行動裝置的通知, 在行動應用程式處於非使用中時, 發生該事件。

Edge 伺服器也包含完全整合的可擴展訊息和目前狀態通訊協定 (XMPP) proxy, 並包含在前端伺服器上的 XMPP 閘道。 您可以設定這些 XMPP 元件, 讓您的商務用 Skype 伺服器使用者可以新增來自以 XMPP 為基礎的合作夥伴的連絡人, 以取得立即訊息和目前狀態。

> [!NOTE]
> XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用, 但商務用 Skype Server 2019 已不再支援。 如需詳細資訊, 請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。

### <a name="mediation-server"></a>中繼伺服器

中繼伺服器是用於實現企業語音、通話和電話撥入式會議所需的元件。 中繼伺服器會轉譯信號, 在某些設定中, 在內部商務用 Skype 伺服器基礎結構與公用交換式電話網絡 (PSTN) 閘道、IP PBX 或會話初始通訊協定 (SIP) 幹線之間的媒體。 您可以在與前臺伺服器相同的伺服器上執行轉送服務伺服器 collocated, 或將它分割成獨立的中繼伺服器池。

如需詳細資訊, 請參閱[商務用 Skype server 中的中繼伺服器元件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。

### <a name="video-interop-server"></a>影片交互操作伺服器

影片交互操作伺服器是商務用 Skype Server 2015 的新角色。 它可讓您將商務用 Skype Server 部署與特定的協力廠商 VTC (Video Teleconferencing 系統) 解決方案整合。 VIS 充當協力廠商電話會議系統與商務用 Skype Server 部署之間的媒介。 在這個版本中, VIS 的重點是使用 Cisco/Tandberg 視頻系統進行互通性。

如需詳細資訊, 請參閱[在商務用 Skype server 中規劃影片互通性伺服器](../../plan-your-deployment/video-interop-server.md)。

### <a name="director"></a>董事

控制器可以驗證商務用 Skype Server 使用者要求, 但不會提供使用者帳戶或提供目前狀態或會議服務。 在能讓外部使用者存取的部署中加強安全性時, 控制器是最實用的。 Director 可以在將要求傳送到內部伺服器前進行驗證。 在拒絕服務攻擊的情況下, 攻擊會以控制器為結束, 而且不會到達前端伺服器。

### <a name="persistent-chat-server-roles"></a>持續聊天伺服器角色

> [!NOTE]
> 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。

持續聊天可讓使用者參與多方、在一段時間內保持的、以主題為基礎的交談。 持續聊天前端伺服器會執行持續聊天服務。 持續式聊天后端伺服器會儲存聊天記錄資料, 以及類別和聊天室的相關資訊。 選用的持續性聊天規範後端伺服器可以儲存聊天內容和相容性事件, 以符合合規性的目的。

執行商務用 Skype Server 標準版的伺服器也可以在同一個伺服器上執行持續聊天 collocated。 您無法 collocate 與企業版前端伺服器的永久聊天前端伺服器。

如需詳細資訊, 請參閱[在商務用 Skype server 2015 中規劃持久聊天伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

## <a name="high-availability-and-disaster-recovery-support"></a>高可用性和災害復原支援

商務用 Skype 伺服器透過 [彙集], 透過伺服器冗余提供高可用性。 如果執行特定伺服器角色的伺服器失敗, 則池中執行相同角色的其他伺服器會載入該伺服器。 這適用于前端伺服器、邊緣伺服器、轉送伺服器和控制器。

商務用 Skype 伺服器也會透過啟用池配對來提供災害復原措施。 如果您部署這個拓朴, 您將會指定一組前端池, 其中每個池都位於另一個資料中心, 且位於不同的地理區域中。 如果有一個池或網站停機, 您可以重新導向該池的使用者, 以使用該集中的其他池, 並最少中斷服務。

商務用 Skype 伺服器也支援後端伺服器高可用性的數個選項。 其中包括下列各項:

- 資料庫鏡像

- AlwaysOn 可用性群組

- AlwaysOn 容錯移轉叢集實例 (FCI)

- SQL 容錯移轉叢集

如需有關池配對及後端伺服器高可用性的詳細資料, 請參閱[在商務用 Skype Server 中規劃高可用性和災難](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)復原。

## <a name="server-collocation-in-skype-for-business-server"></a>商務用 Skype Server 中的 [伺服器 collocation]

我們已使用過字詞 collocate, 但這代表什麼意思？ 商務用 Skype Server 可讓您找出在同一台伺服器 (也就是 collocation 或不同的伺服器) 上的部分伺服器角色和功能, 但在您開始時可能會造成混淆, 以及您是執行標準版還是企業版伺服器部署 (它們各自都有自己的規則)。 為了協助您的規劃, 我們在標準版伺服器部署和企業版的前端池部署中包含伺服器 collocation (在大多數情況下, 這項資訊是完全相同的, 而且在哪裡有所不同, 就是特別指出的)。

### <a name="collocation-of-server-roles"></a>伺服器角色的 Collocation

標準版伺服器具有下列角色 collocated (不過還需要進行其他設定), 而在企業版前端池中, 此角色可以是 collocated, 或部署到個別的伺服器:

- 仲介

每個伺服器角色都必須部署在個別的伺服器上:

- 董事

- 左邊

- 影片交互操作伺服器

- Office Web Apps

### <a name="databases"></a>資料庫

這是標準版伺服器部署與企業版伺服器池部署之間實際差異的區域, 因此我們將提供兩個區段, 後面再加上一些其他規則。

#### <a name="standard"></a>標準

因為 SQL Server Express 是在標準版伺服器上 collocated, 而且無法移動, 所以這相當簡單。 此外, 如果您在標準版伺服器上部署持久聊天伺服器, 您也可以在標準版伺服器上 collocate 持續聊天和持續聊天合規性資料庫, 但您不需要。

> [!NOTE]
> 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。

這些不能在標準版 server 上 collocated, 但可以在單一資料庫伺服器上繼續使用:

- 監控資料庫

- 封存資料庫

- 企業版前端池的任何後端資料庫

#### <a name="enterprise"></a>級

下列資料庫可以在同一個後端 SQL Server 上 collocated:

- 後端資料庫

- 監控資料庫

- 封存資料庫

- 持續聊天資料庫

- 持續聊天合規性資料庫

#### <a name="both"></a>同時

現在, 當您 collocating 單一 SQL 實例中的商務用 Skype Server 資料庫, 或同一 SQL Server 資料庫中的多個 SQL 實例時, 還有一些其他規則:

- 每個 SQL 實例只能包含企業版前端池的單一後端資料庫、單一監視資料庫、單一封存資料庫、單一持續式聊天資料庫, 以及單一持續聊天合規性資料庫。

- 資料庫伺服器不支援一個以上的企業版前端池、一個伺服器執行封存、一個伺服器執行監視、單一持久性聊天資料庫, 以及單一持續聊天合規性資料庫, 但它可以支援其中一個專案,不論資料庫是使用相同的 SQL Server 實例, 還是要使用不同的 SQL Server 實例。

    > [!NOTE]
    > 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。

### <a name="file-shares"></a>檔案共用

檔案共用可以在不同的伺服器上, 也可以在同一個伺服器上 collocate, 就像下列任一或所有專案:

- 資料庫伺服器, 包括企業版頂層端池的後端伺服器

- 監控資料庫

- 封存資料庫

- 持續聊天資料庫

- 持續聊天合規性資料庫

> [!CAUTION]
> 請注意, 雖然您可以在這些伺服器上 collocate 檔案共用, 但請務必注意, 我們不建議您這麼做。 如果您要與任何其他伺服器角色 collocating 檔案共用, 請務必定期監視磁碟空間與效能問題。

### <a name="keep-in-mind"></a>切記

- 您無法 collocate 反向 proxy 伺服器 (不是商務用 Skype Server 元件), 甚至可能不會在您的拓撲中。 如果您想要支援共同處理共同使用者的網頁內容, 您需要使用反向 proxy。 如果您需要, 請先設定貴組織中已供其他應用程式使用的現有反向 proxy 伺服器, 以取得商務用 Skype 伺服器的反向 proxy 支援。

- 您無法 collocate 任何 Exchange UM 元件或 SharePoint Server 元件 (含任何商務用 Skype Server 角色)。

## <a name="see-also"></a>另請參閱

[商務用 Skype Server 的參考拓撲](reference-topologies.md)
