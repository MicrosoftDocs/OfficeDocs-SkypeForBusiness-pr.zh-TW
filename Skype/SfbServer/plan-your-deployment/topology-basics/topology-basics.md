---
title: 商務用 Skype Server 的拓撲基礎
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 摘要：選擇您的商務用 Skype 伺服器拓撲。 瞭解適用于商務用 Skype Server 的伺服器組合。
ms.openlocfilehash: 9b0dbe6a74a5982c2816c022e5ea7a99ba2abf07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831753"
---
# <a name="topology-basics-for-skype-for-business-server"></a>商務用 Skype Server 的拓撲基礎

**摘要：** 選擇您的商務用 Skype 伺服器拓撲。 瞭解適用于商務用 Skype Server 的伺服器組合。

準備其他任何專案之前，您會想要知道您在規劃商務用 Skype Server 的部署的正確拓撲。 您必須決定的第一件事是，如果您要部署商務用 Skype Server 的內部部署，或是您想要將此功能與混合式部署中的商務用 Skype Server Online 部署結合使用。 無論是哪一種方式，您都會想進一步閱讀，因為我們會在這裡詳述內部部署拓撲，但混合式詳細資料會記錄在其專屬的區段中。

您也可以在 [商務用 Skype Server 的參考拓撲](reference-topologies.md)中查看一些範例拓撲。

## <a name="sites"></a>網站

在商務用 Skype Server 中，您可以在網路上定義包含商務用 Skype 伺服器元件的網站。 網站是以高速、低延遲網路來妥善連線的一組電腦，例如單一區域網路 (LAN) 或以高速光纖網路連接的兩個網路。 請注意，商務用 Skype 伺服器網站是來自 Active Directory 網域服務網站和 Microsoft Exchange Server 網站的不同概念。 您的商務用 Skype 伺服器網站不需要對應至您的 Active Directory 網站。

商務用 Skype 伺服器支援內部部署一或多個網站，可根據您的高可用性和位置需求進行調整。

您的部署至少有一個中央網站 (也稱為資料中心，這是) 中所有伺服器的資料中心，而部署中的每個中央網站都有一個 Standard Edition server，或至少一個 Enterprise Edition 前端集區。 您可以在下列每個選項中看到差異：

- Standard Edition server 包含組合 SQL Server Express 資料庫。

- Enterprise Edition 前端集區包括：

  - 一或多部前端伺服器 (理想情況下至少三個，可伸縮性) ，最多為12個。 有一部以上的伺服器需要進行負載平衡。

  - 個別的後端伺服器。

您可以在本節稍後深入瞭解各種伺服器角色。

除了您的中央網站之外，您還可以建立一個或多個與中央網站相關聯的分支網站。 它們主要取決於中央網站，以取得幾乎所有的功能，因此它們是由哪些專案所組成？

- Survivable 分支裝置，將公用交換電話網路 (PSTN) 閘道與某些商務用 Skype Server 功能結合在一起。

- Survivable 分支伺服器是執行 Windows Server 的伺服器，該伺服器已安裝商務用 Skype Server 註冊機構和轉送伺服器軟體。

- 獨立的 PSTN 閘道 (，不屬於 Survivable 分支裝置) 。

- 如果您不想要使用 Survivable Branch) 裝置組合此角色，請使用獨立轉送伺服器或獨立轉送伺服器集區 (。

## <a name="whats-in-a-skype-for-business-server-site"></a>商務用 Skype Server 網站有哪些功能？

若要深入瞭解詳細資訊，中央網站也可以使用：

- 在相同網域或不同網域中的多個前端集區 (請記住，在規劃前端集區中的所有前端伺服器，以及集區的後端伺服器，都必須位於相同的網域中) 。

- 多部 Standard Edition Server。

- Office Web Apps Server，可用於商務用 Skype Server 中的 Office Web Apps，以用於共用及呈現 PowerPoint 簡報。

- 周邊網路) 中的 edge Server 或 Edge 集區 (。 如果您想要部署支援同盟協力廠商、公用 IM 連線、可延伸的訊息和顯示狀態通訊協定 (XMPP) 閘道和遠端使用者存取，則需要。 您可以在 Edge Server 規劃檔中找到詳細資訊。

- Persistent Chat Server。 如果您想要讓使用者能夠加入一段時間內，以主題為基礎的會話，則會很有用。 在「Persistent Chat Server」主題中有其他資訊。

- 監測。 用來支援音訊/視頻的資料收集 (A/V) 的經驗品質 (QoE) 及通話詳細資料記錄 (CDR) 在您的部署中的企業語音和 A/V 會議。 我們會在規劃監控主題時詳細討論它。

- Director 或 Director 集區。 不需要，但是如果您想要提升復原能力並啟用商務用 Skype 使用者要求重新導向至使用者的主集區，則此方法很有用。 如果您想要部署 Director，則每個集區最多可支援10個。 如果這是您需要的專案，請務必繼續閱讀「董事會規劃」主題。

- 反向 proxy。 這不是商務用 Skype Server 元件，但是如果您想要支援同盟使用者的 web 內容共用，您若想要支援行動性流量，如果您想要支援行動性流量，您可以在環境中執行這項操作。 有一個設定反向 proxy 伺服器主題，當您準備好時，您可以查看更多詳細資料。

您可以在下列伺服器上找到組合的其他資訊。

在您的中央網站上部署的所有前端集區和 Standard Edition 伺服器，假設您已部署下列各項：

||||
|:-----|:-----|:-----|
|Director 或 Director 集區  <br/> |獨立轉送伺服器或轉送伺服器集區  <br/> |Office Web Apps Server  <br/> |
|Edge Server 或 Edge 集區  <br/> |Persistent Chat Server 或 Persistent Chat Server 集區  <br/> |監視  <br/> |

在此清單中，Exchange 整合通訊 (UM) 伺服器在哪裡？ 當然，如果您想要與 Exchange UM 整合，但它不是商務用 Skype Server 網站的元件，您當然也可以使用它，因此我們不會在這裡提及。

您可能會規劃多個中央網站，如果是的話，他們可以在您的中央網站上共用下列伺服器和角色：

|||
|:-----|:-----|
|獨立轉送伺服器或轉送伺服器集區  <br/> |Edge Server 或 Edge 集區  <br/> |
|Persistent Chat Server 或 Persistent Chat Server 集區  <br/> |監視  <br/> |

就像最後一個清單一樣，我們不會在這裡包含 Exchange UM 伺服器，因為這不是商務用 Skype Server 部署的一部分，但也在這裡也屬於相同的類別。

當然，還有其他一些元件和選項會進入部署。

|||||
|:-----|:-----|:-----|:-----|
|防火牆  <br/> |當您部署企業語音時， (PSTN 閘道  <br/> |Exchange UM Server (如果您想要與 Exchange UM 整合)   <br/> |DNS 負載平衡  <br/> |
|硬體負載平衡器  <br/> |SQL Server 資料庫  <br/> |檔案共用  <br/> ||

## <a name="server-roles"></a>伺服器角色

每一部執行商務用 Skype 伺服器的伺服器都會執行一或多個伺服器角色。 伺服器角色是該伺服器所提供之商務用 Skype Server 功能的定義集合。 您不需要在您的網路中部署所有可用的伺服器角色。 只安裝包含您想要之功能的伺服器角色。

針對大部分的伺服器角色，針對可擴充性和高可用性，您可以部署多部伺服器的集區，所有執行相同的伺服器角色。 集區中的每部伺服器都必須執行一或多個相同的伺服器角色。 對於商務用 Skype Server 中的大部分類型的集區，您必須部署負載平衡器，以散佈集區中各種伺服器間的流量。 商務用 Skype 伺服器支援網域名稱系統 (DNS) 負載平衡與硬體負載平衡器。

### <a name="front-end-server-and-back-end-server"></a>前端伺服器及後端伺服器

在商務用 Skype Server Enterprise Edition 中，前端伺服器是核心伺服器角色，而且會執行許多基本商務用 Skype Server 功能。 在任何商務用 Skype Server Enterprise Edition 部署中，前端伺服器及後端伺服器都是唯一需要的伺服器角色。

前端集區是一組前端伺服器（已正確設定），可共同運作，以提供通用使用者群組的服務。 執行相同角色的多部伺服器集區提供可擴充性和容錯移轉功能。

前端伺服器包含下列專案：

- 使用者驗證和註冊。

- 目前狀態資訊和連絡人卡片交換。

- 通訊錄服務和通訊群組清單擴充。

- IM 功能（包括多方 IM 會議）。

- Web 會議、PSTN 電話撥入式會議和 A/V 會議 (（若已部署) ）。

- 應用程式裝載（適用于商務用 Skype (Server 所包含的兩個應用程式）例如會議助理和回應群組應用程式) ，以及協力廠商應用程式。

- （選用）監控，以 [通話詳細資料記錄] 的形式收集使用資訊 (Cdr) 並呼叫錯誤記錄 (Cer) 。 此資訊提供有關媒體質量 (音訊和影片) 針對企業語音通話和 A/V 會議進行網路的統計資料。

- 網頁元件至支援的 web 工作，例如 web 排程器及加入啟動器。

- （選用）封存 IM 通訊和會議內容，以符合合規性的原因。 如需詳細資訊，請參閱規劃檔中的 [規劃](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) 封存。

    在 Lync Server 2010 和舊版中，監控和封存是不同的伺服器角色，不會組合在前端伺服器上。

- （選用）啟用持續性聊天時，會持續聊天網頁服務用於聊天室管理，並可進行檔案上傳/下載的持續性聊天 Web 服務。

前端集區也是使用者和會議資料的主要儲存區。 每個使用者的資訊都會在集區中的三部前端伺服器之間進行複製，並在後端伺服器上備份。

此外，部署中的一部前端伺服器也會執行中央管理伺服器，此伺服器會管理及部署所有執行商務用 Skype Server 之伺服器的基本設定資料。 中央管理伺服器也提供 Lync Server 管理命令介面和檔案傳輸功能。

後端伺服器是執行 Microsoft SQL Server 的資料庫伺服器，提供前端集區的資料庫服務。 後端伺服器充當集區使用者和會議資料的備份存放區，也是其他資料庫（如回應群組資料庫）的主要儲存區。 您可以擁有單一的後端伺服器，但在進行容錯移轉時，建議使用 [商務用 Skype server 的後端伺服器高可用性](../high-availability-and-disaster-recovery/back-end-server.md) 。 後端伺服器不會執行任何商務用 Skype Server 軟體。

> [!IMPORTANT]
> 我們不建議使用其他資料庫組合商務用 Skype Server 資料庫。 如果您這麼做，可用性和效能可能會受到影響。

> [!NOTE]
> 在商務用 Skype 2015 Server 中可使用 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) ，以及使用商務用 Skype Server 2019 的首選 SQL 容錯移轉叢集方法。

儲存在後端伺服器資料庫中的資訊包括目前狀態資訊、使用者的連絡人清單、會議資料（包括所有目前會議狀態的持續性資料）和會議排程資料。

### <a name="edge-server"></a>Edge Server

Edge Server 可讓您的使用者與組織防火牆外的使用者進行通訊及共同作業。 這些外部使用者可以包含組織的使用者，這些使用者目前正在異地工作、同盟夥伴組織的使用者，以及已被邀請加入您的商務用 Skype Server 部署會議的外部使用者。

部署 Edge Server 也會啟用行動裝置，其支援行動裝置上的 Lync 功能。 使用者可以使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置執行活動，例如傳送和接收立即訊息、查看連絡人及查看顯示狀態。 此外，行動裝置還可支援某些 Enterprise Voice 功能，例如按一下加入會議、從公司撥號、單一號碼搜尋、語音信箱及未接來電。 行動功能也可以為不支援在背景執行應用程式的行動裝置，支援「推播通知」。 推播通知是針對在行動應用程式為非使用中狀態時所發生的事件，傳送給行動裝置的通知。

Edge Server 也包含完整整合的可延伸訊息和顯示狀態通訊協定 (XMPP) proxy，包含在前端伺服器上的 XMPP 閘道。 您可以設定這些 XMPP 元件，讓商務用 Skype 伺服器使用者新增來自以 XMPP 為基礎的合作夥伴的連絡人，以進行立即訊息及顯示狀態。

> [!NOTE]
> XMPP 閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。

### <a name="mediation-server"></a>中繼伺服器

轉送伺服器是用來執行企業語音、呼叫公司電話和電話撥入式會議的必要元件。 轉送伺服器轉譯信號，在某些設定中，在內部商務用 Skype 伺服器基礎結構和公用交換電話網路 (PSTN) 閘道、IP-PBX 或會話初始通訊協定 (SIP) 主幹之間的媒體。 您可以在前端伺服器所在的伺服器上執行轉送伺服器組合，或將其分割成獨立的轉送伺服器集區。

如需詳細資訊，請參閱 lync server [component In 商務用 Skype server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。

### <a name="video-interop-server"></a>視訊互通性伺服器

影片 Interop 伺服器是商務用 Skype Server 2015 的新角色。 它可讓您將商務用 Skype 伺服器部署與特定協力廠商 VTC (Video 電話會議 System) 解決方案進行整合。 VIS 充當協力廠商電話會議系統和商務用 Skype Server 部署之間的媒介。 在此版本中，VIS 著重于與 Cisco/Tandberg 影片系統的互通性。

如需詳細資訊，請參閱 [在商務用 Skype server 中規劃影片 Interop 伺服器](../../plan-your-deployment/video-interop-server.md)。

### <a name="director"></a>Director

Director 可驗證商務用 Skype Server 使用者要求，但不會家用使用者帳戶或提供目前狀態或會議服務。 Director 在啟用外部使用者存取的部署中增強安全性是非常有用的。 Director 可以在將要求傳送至內部伺服器之前先驗證要求。 在拒絕服務攻擊的情況下，攻擊會以 Director 結尾，而且不會到達前端伺服器。

### <a name="persistent-chat-server-roles"></a>Persistent Chat Server Role

> [!NOTE]
> 商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。 小組中提供相同的功能。 如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。

Persistent chat 可讓使用者加入一段時間內的多方、主題型交談。 Persistent Chat 前端伺服器會執行 persistent chat service。 Persistent Chat 後端伺服器會儲存聊天記錄資料，以及類別和聊天室的相關資訊。 選用的持續性聊天規範後端伺服器可以儲存聊天內容和符合性事件，以符合規範的目的。

執行商務用 Skype Server Standard Edition 的伺服器也可以在同一部伺服器上執行 Persistent chat 組合。 您無法以 Enterprise Edition 前端伺服器組合持久聊天前端伺服器。

如需詳細資訊，請參閱 [Plan For Persistent Chat server In 商務用 Skype server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

## <a name="high-availability-and-disaster-recovery-support"></a>高可用性和嚴重損壞修復支援

商務用 Skype 伺服器透過 pooling 透過伺服器的冗余度，提供高可用性。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。 這適用於前端伺服器、Edge Server、中繼伺服器和 Director。

商務用 Skype 伺服器也會啟用集區配對，以提供嚴重損壞修復措施。 如果您部署這個拓樸，將會指定前端集區配對，每一對中各個集區都位在不同的資料中心，並且在不同的地理區。 如果一個集區或網站故障，您可以重新導向該集區的使用者，以使用該配對中另一個集區，讓服務中斷時間降至最低。

商務用 Skype 伺服器也支援多種選項，以供後端伺服器高可用性之用。 包括下列各項：

- 資料庫鏡像

- AlwaysOn 可用性群組

- AlwaysOn (FCI 的容錯移轉叢集實例) 

- SQL 容錯移轉叢集

如需有關集區配對及後端伺服器高可用性的詳細資訊，請參閱 [在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。

## <a name="server-collocation-in-skype-for-business-server"></a>商務用 Skype Server 中的伺服器組合

我們已使用字片語合，但這是什麼意思？ 商務用 Skype Server 可讓您在同一部伺服器上尋找一些伺服器角色和功能，也就是在不同的伺服器上組合，但在您開始時，可能會造成混淆，以及您要執行的是 Standard Edition 還是 Enterprise Edition Server 部署 (各自都附帶各自的規則) 。 為了協助您進行規劃，我們包括 Standard Edition server 部署和 Enterprise Edition 前端集區 (部署中的伺服器組合。在大多數情況下，這項資訊是相同的，而且在不同的地方，稱為特別) 。

### <a name="collocation-of-server-roles"></a>伺服器角色的組合

Standard Edition server 具有下列角色組合 (其他設定也是) ，但在 Enterprise Edition 前端集區中，此角色可以組合，或部署至不同的伺服器：

- 調解

這些伺服器角色必須分別部署在不同的伺服器上：

- Director

- 銳利

- 視訊互通性伺服器

- Office Web Apps

### <a name="databases"></a>資料庫

這是 Standard Edition server 部署和 Enterprise Edition server 集區部署之間的實際差異區域，因此我們將會有兩個區段，後面接著提供一些額外的規則。

#### <a name="standard"></a>標準版

因為 SQL Server Express 是在 Standard Edition Server 上組合，而且無法移動，所以這相當簡單。 此外，如果您在 Standard Edition server 上部署 Persistent Chat Server，您也可以組合 Standard Edition server 上的持續聊天和持續性聊天規範資料庫，但您不需要這樣做。

> [!NOTE]
> 商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。 小組中提供相同的功能。 如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。

這些無法在 Standard Edition server 上組合，但可以繼續使用自己的單一資料庫伺服器：

- 監控資料庫

- 封存資料庫

- Enterprise Edition 前端集區的任何後端資料庫

#### <a name="enterprise"></a>Enterprise

下列資料庫可以在同一部後端 SQL Server 上組合：

- 後端資料庫

- 監控資料庫

- 封存資料庫

- Persistent Chat 資料庫

- Persistent Chat 規範資料庫

#### <a name="both"></a>兩者都要

現在，當您在單一 SQL 實例中組合商務用 Skype Server 資料庫，或在相同 SQL Server 資料庫的多個 SQL 實例中，請遵循下列其他規則：

- 每個 SQL 實例僅可包含 Enterprise Edition 前端集區的單一後端資料庫、單一監控資料庫、單一封存資料庫、單一持久聊天資料庫及單一持久聊天規範資料庫。

- 資料庫伺服器不支援一個以上的 Enterprise Edition 前端集區、一部執行封存的伺服器、單一持久聊天資料庫，以及單一 Persistent Chat 規範資料庫，但不論資料庫使用相同的 SQL Server 實例，還是使用不同的 SQL Server 實例，都可以支援其中一個。

    > [!NOTE]
    > 商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。 小組中提供相同的功能。 如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。

### <a name="file-shares"></a>檔案共用

檔案共用可以位於不同的伺服器上，也可以在與下列任何或所有專案相同的伺服器上組合：

- 資料庫伺服器，包括 Enterprise Edition 前端集區的後端伺服器

- 監控資料庫

- 封存資料庫

- Persistent Chat 資料庫

- Persistent Chat 規範資料庫

> [!CAUTION]
> 請注意，雖然您可以在這些伺服器上組合檔案共用，但是請務必注意，我們不建議您這樣做。 如果您要組合任何其他伺服器角色的檔案共用，請務必定期監控磁碟空間和效能問題。

### <a name="keep-in-mind"></a>請記住

- 您無法組合反向 proxy 伺服器，這不是商務用 Skype Server 元件，甚至可能不會在您的拓撲中。 如果您想要支援同盟使用者的 web 內容共用，以及許多其他專案，則需要反向 proxy。 如有需要，請在您的組織中，設定其他應用程式所使用的現有反向 proxy 伺服器，繼續並為商務用 Skype 伺服器實施反向 proxy 支援。

- 您無法組合任何 Exchange UM 元件或使用任何商務用 Skype Server 角色的 SharePoint 伺服器元件。

## <a name="see-also"></a>另請參閱

[商務用 Skype Server 的參考拓撲](reference-topologies.md)
