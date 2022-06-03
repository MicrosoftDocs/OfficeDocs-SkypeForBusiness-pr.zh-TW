---
title: 在 商務用 Skype Server 中建立和發佈新的拓撲
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 451c41a1-b8c5-4dc3-9e48-0da9ed5381a1
description: 摘要：瞭解如何在安裝商務用 Skype Server之前建立、發佈及驗證新的拓撲。
ms.openlocfilehash: 9ae6ee05a20f75946a87e611e972341094a11864
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860554"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>在 商務用 Skype Server 中建立和發佈新的拓撲
 
**總結：** 瞭解如何在安裝商務用 Skype Server之前建立、發佈及驗證新的拓撲。
  
您必須先建立拓撲併發布拓撲，才能在拓撲的每部伺服器上安裝商務用 Skype Server系統。 當您發佈拓撲時，會將拓撲資訊載入中央管理Microsoft Store資料庫。 如果這是Enterprise Edition集區，您會在第一次發佈新拓撲時建立中央管理Microsoft Store資料庫。 如果Standard Edition，您必須在發佈拓撲之前，先從部署精靈執行 [準備第一個Standard Edition伺服器] 程式。 這會藉由安裝 SQL Server Express Edition 實例並建立中央管理Microsoft Store來準備Standard Edition。 您可以依任何循序執行步驟 1 到 5。 不過，您必須依序執行步驟 6、7 和 8，以及步驟 1 到 5 之後，如圖表中所述。 步驟 8 的步驟 6 說明如何建立和發佈新的拓撲。
  
![概觀圖表。](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>建立和發佈新拓撲

您可以使用商務用 Skype Server拓撲產生器來設計、定義、設定及發佈拓撲。 當您稍早在本文中安裝系統管理工具時，已安裝此工具。 建立拓撲時，您可以進行許多不同的選擇。 在此程式中，您將使用會議建立基本拓撲。
  
> [!IMPORTANT]
> 商務用 Skype Server需要SQL Server才能運作。 主資料庫稱為中央管理Microsoft Store。 如果您要部署Enterprise Edition，當您使用下列步驟發佈拓撲時，就會建立這些資料庫。 在此情況下，拓撲產生器會要求您提供SQL Server安裝的連線資訊。 如果您打算部署Standard Edition，您必須先安裝 SQL Server Express Edition，才能定義和發佈新的拓撲。 若要安裝 SQL Server Express 版，您應該在將作為前端的伺服器上開啟 [部署精靈]，然後執行 [準備第一個Standard Edition伺服器]。 當您按一下 [準備第一個Standard Edition伺服器] 時，[部署精靈] 會自動安裝 SQL Server Express 版本，並建立中央管理Microsoft Store資料庫。 
  
### <a name="create-a-new-topology"></a>建立新的拓撲

1. 以具有拓撲產生器存取權的標準使用者身分登入。
    
2. 開商務用 Skype Server拓撲產生器。
    
3. 選 **取 [新增拓撲]**，然後按一下 [ **確定]**。
    
4. 選取拓撲組態檔的位置和檔案名。
    
    > [!NOTE]
    > 拓撲組態會儲存為拓撲產生器 XML (.tbxml) 檔案。 當您發佈拓撲時，會將組態資訊從檔案推送至SQL Server資料庫。 當您未來開啟拓撲產生器時，可以將現有的設定從SQL Server直接下載到拓撲產生器，然後將它發佈回SQL Server，或將它儲存為拓撲產生器組態檔。 
  
5. 在 [ **定義主域] 畫面上**，輸入 **主要 SIP 網域**，然後按 [ **下一步]**。 在此範例中，我們會使用 `contoso.local` ，如圖所示。
    
     ![定義主要 sip 網域。](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. 新增任何其他支援的 SIP 網域，然後按 [ **下一步]**。
    
7. 輸入第一個網站 (位置) 的 [ **名稱** ] 和 [ **描述** ]，然後按 [ **下一步**]，如圖所示。
    
     ![定義第一個網站 (位置) 。](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. 輸入網站的 **[城市**]、 **[州/省**] 和 [ **國家/地區代碼** ]，然後按 [ **下一步]**。
    
9. 按一下 **[完成** ] 以完成定義新拓撲的程式。 [新增前端精靈] 會自動啟動。
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>定義前端集區或Standard Edition伺服器

1. 檢閱精靈必要條件，然後按 [ **下一步]**。
    
2. 輸入集區 FQDN)  (完整功能變數名稱，然後選 **取 [Enterprise Edition前端集區**] 或 **[Standard Edition Server**]，然後按 [**下一步**]，如圖所示。
    
    > [!TIP]
    > 商務用 Skype Server Enterprise Edition可以包含多部一起運作以提供前端角色的伺服器。 當使用多部伺服器來履行角色時，它稱為集區。 因此，多部伺服器一起運作以提供前端角色也稱為前端集區。 商務用 Skype Server Standard Edition只能包含單一伺服器來提供前端角色。 即使只有單一伺服器提供角色，也經常會參考前端集區。 
  
     ![定義前端集區。](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. 輸入集區中所有電腦 (FQDN) 的完整功能變數名稱，然後按 [ **下一步** ]，如圖所示。
    
     ![定義集區中的電腦。](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. 選取將包含在此拓撲中的功能，然後按 [ **下一步** ]，如圖所示。
    
    > [!NOTE]
    > 商務用 Skype Server包含許多進階功能。 檢閱您想要使用之每個特定功能的規劃和部署檔。 
  
     ![選取部署的功能。](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. 在 [ **選取共置的伺服器角色** ] 頁面上，您可以選擇在前端伺服器上共置轉送伺服器，也可以選擇將它部署為獨立伺服器。
    
    如果您想要在Enterprise Edition前端集區上共置轉送伺服器，請確定已選取核取方塊。 伺服器角色將會部署在集區伺服器上。 如果您想要將轉送伺服器部署為獨立伺服器，請清除適當的核取方塊。 在您完全部署前端伺服器之後，您會在個別的部署步驟中部署轉送伺服器。 如需共置的規劃詳細資料，請參閱[商務用 Skype Server 的拓撲基本概念](../../plan-your-deployment/topology-basics/topology-basics.md)。
    
6. 藉由使用 [ **將伺服器角色與這個前端集區建立關聯** ] 頁面，您可以定義伺服器角色並與前端集區建立關聯。 下列角色可供使用：
    
    **啟用 Edge 集區** 定義單一 Edge Server 或 Edge Server 集區並建立關聯。 Edge Server 有助於組織內部使用者與組織外部人員之間的通訊和共同作業，包括同盟使用者。
    
    您可以使用兩種可能的案例來部署伺服器角色並建立關聯。
    
    在案例一當中，您可以為全新安裝定義新的拓撲。 您可以透過下列兩種方式之一來進行安裝：
    
   - 讓核取方塊保持清楚，並定義拓撲。 發佈、設定及測試前端和後端伺服器角色之後，您可以再次執行拓撲產生器，將角色服務器新增至拓撲。 藉由使用此策略，您可以測試前端集區和執行SQL Server的伺服器，而不需要其他角色的額外複雜性。 完成初始測試之後，您可以再次執行拓撲產生器，以選取您需要部署的角色。
    
   - 選取您需要安裝的角色，然後設定硬體以容納選取的角色。
    
     針對第二個案例，您有現有的部署，且基礎結構已準備好供新角色使用，或者您需要將現有角色與新的前端伺服器建立關聯。
    
   - 在此情況下，您將選取要部署或與新前端伺服器建立關聯的角色。 不管是哪一種情況，您都需要先定義角色並設定需要的硬體後，才開始安裝。
    
7. 接下來，您將定義將與拓撲搭配使用的SQL Server存放區。 在此範例中，我們會使用預設實例。 如需SQL Server功能的詳細資訊，例如高可用性，請參閱[規劃商務用 Skype Server中的高可用性和災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
    
   - 若要使用已在拓撲中定義的現有SQL Server存放區，請從 **SQL存放** 區中選取實例。
    
   - 若要定義新的SQL Server實例來儲存集區資訊，請按一下 [**新增**]，然後在 [**定義新** SQL Microsoft Store] 對話方塊中指定 **SQL Server FQDN**。
    
   - 若要指定SQL Server實例的名稱，請選取 [**具名實例**]，然後指定實例的名稱。
    
   - 若要使用預設實例，請按一下 **[預設實例]**。
    
   - 若要使用SQL鏡像，請選 **取 [啟用SQL鏡像**]，然後選取現有的實例，或建立新的實例。

     > [!NOTE]
     > SQL鏡像可在 2015 商務用 Skype Server使用，但在 2019 商務用 Skype Server不再支援。 商務用 Skype Server 2019 偏好使用 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) ，以及SQL容錯移轉叢集方法。
    
     在此範例中，我們會輸入 **SQL Server FQDN**，並設定任何相關的高可用性設定，然後按一下 [**確定]**，如圖所示。
    
     ![建立SQL Server存放區。](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. 決定是否要啟用SQL Server儲存鏡像或SQL Server鏡像見證，然後按 [**下一步]**。
    
9. 定義您想要使用的檔案共用。
    
   - 若要使用拓撲中已經定義的檔案共用，選取 **[使用先前定義的檔案共用]**。
    
   - 若要定義新的檔案共用，請選取 [ **定義新的檔案共用]**，在 [ **檔案伺服器 FQDN]** 方塊中，輸入檔案共用所在之現有檔案伺服器的 FQDN，然後在 [ **檔案共用** ] 方塊中輸入檔案共用的名稱。
    
     在此範例中，我們將按一下 **[定義新的檔案存放區]**，輸入 **檔案伺服器 FQDN** 和 **檔案共用**，然後按 [ **下一步]**。
    
     > [!NOTE]
     > 商務用 Skype Server的檔案共用可以共置，但不建議基於效能考慮。 請注意，在此範例中，檔案共用已位於將作為檔案共用的單一專用伺服器上。 不過，建議使用其他更健全的檔案共用系統，例如使用 Windows Server 2012 R2 的 DFS。 如需支援檔案共用系統的詳細資訊，請參閱[商務用 Skype環境的需求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 如需建立檔案共用的詳細資訊，請參閱[在 商務用 Skype Server 中建立檔案共用](create-a-file-share.md)。 您不需要先建立檔案共用，就能定義檔案共用。 在您發行拓撲之前，必須先在定義檔案共用的位置上加以建立。 
  
10. 在 [指定 Web 服務 URL] 頁面上，您必須決定是否需要覆寫內部 Web 服務集區基底 URL。 此覆寫的原因必須與負載平衡有關。 基本 SIP 流量可以透過簡單的 DNS 負載平衡來進行負載平衡。 不過，HTTP/S Web 服務網路流量必須使用支援的硬體或軟體負載平衡解決方案。 如需支援的負載平衡器，請參閱[商務用 Skype的基礎結構](../../../SfbPartnerCertification/certification/infra-gateways.md)。 在此範例中，我們使用 SIP 流量的 DNS 負載平衡，以及支援的軟體負載平衡解決方案。 因為我們要以這種方式分割流量，所以我們必須覆寫內部 Web 服務集區 FQDN。 或者，如果我們有最上層負載平衡器，並透過它傳送所有流量，而不是針對 SIP 流量使用 DNS 負載平衡，則不需要覆寫 Web 服務 URL。 
    
    在本主題的 DNS 區段中，我們建立了 的 `webint.contoso.local` A 記錄。 這是我們用於 Web 服務 HTTP/S 流量的 URL，它必須經過我們設定的支援軟體負載平衡器。 因此，在此範例中，我們會覆寫 URL，讓商務用 Skype Server知道所有 HTTP/S 流量都應該移至 `webint.contoso.local` ，而不是 `pool.contoso.local` ，如圖所示。 如需負載平衡的詳細資訊，請參閱[商務用 Skype的負載平衡需求](../../plan-your-deployment/network-requirements/load-balancing.md)。
    
    > [!IMPORTANT]
    > 基底 URL 是 URL 的 Web 服務識別身分，去除 https://。 例如，如果集區 Web 服務的完整 URL 為 `https://webint.contoso.local` ，則基底 URL 為 `webint.contoso.local` 。 
  
    - 如果您要設定 DNS 負載平衡，如我們在此範例中所示，請選取 [ **覆寫內部 Web 服務集區 FQDN** ] 核取方塊，然後輸入內部基底 URL (必須與 **內部基底 URL** 中的集區 FQDN) 不同。 
    
    > [!CAUTION]
    > 如果您決定使用自我定義的 FQDN 覆寫內部 Web 服務，則每個 FQDN 必須是任何其他前端集區、目錄或目錄集區中的唯一 FQDN。 當您定義 URL 或完整功能變數名稱時，**請只 (使用標準字元**，包括 A-Z、a-z、0-9 和連字號) 。 請勿使用 Unicode 字元或底線。 外部 DNS 和公開憑證授權單位單位通常不支援 URL 或 FQDN 中的非標準字元， (CA)  (也就是說，當 URL 或 FQDN 必須指派給憑證) 中的主體名稱或主體別名時。
  
    - 選擇性地在 [外部基底 URL] 中輸入 **外部基底 URL**。 您會輸入外部基底 URL，以區別內部功能變數名稱。 例如，您的內部網域是 `contoso.local` ，但您的外部功能變數名稱是 `contoso.com` 。 您會使用 `contoso.com` 功能變數名稱來定義 URL，因為它必須可從公用 DNS 解析。 在反向 Proxy 的情況中，這種作法也很重要。 外部基底 URL 功能變數名稱會與反向 Proxy FQDN 的功能變數名稱相同。 若要在行動用戶端上立即訊息和存在，必須要有前端集區的 HTTP 存取權。
    
      ![覆寫 Web 服務。](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. 如果您在 [**選取功能**] 頁面上選取 [**會議**]，系統會要求您選取Office Web Apps伺服器。 按一下 **[新增** ] 以啟動對話方塊。
    
12. 在 [**定義新Office Web Apps伺服器**] 對話方塊的 [Office Web Apps Server FQDN] 方塊中輸入 **Office Web Apps伺服器的 FQDN**;當您這麼做時，Office Web Apps 伺服器探索 URL 應該會自動輸入到 **[Office Web Apps 伺服器探索 URL]** 方塊中。
    
    如果Office Web Apps伺服器安裝在內部部署且與商務用 Skype Server相同的網路區域中，請勿選 **取 [Office Web Apps伺服器部署在外部網路 (，也就是周邊/網際網路)** 選項。
    
    如果Office Web Apps伺服器部署在內部防火牆外部，請選 **取 [Office Web Apps伺服器部署在外部網路 (，也就是周邊/網際網路)** 選項。
    
13. 按一下 **[完成** ] 以完成設定。 如果您在 [ **將伺服器角色與這個前端集區建立關聯** ] 頁面上定義了其他角色服務器，則會開啟個別的角色設定精靈頁面，您可以在其中設定伺服器角色。 在此範例中，我們只選擇會議。
    
### <a name="configure-simple-urls"></a>設定簡單的 URL

1. 在 [拓撲產生器] 中，以滑鼠右鍵按一下 **頂端節點商務用 Skype Server**，然後按一下 [**編輯屬性**]，如圖所示。
    
     ![以滑鼠右鍵按一下 [商務用 Skype Server]，然後選取 [編輯屬性]。](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. 在 [**簡單 URL**] 窗格中，選 **取 [電話存取 URL：** (撥入) 或 **會議 URL：** ([符合) ] 進行編輯，然後按一下 [**編輯 URL]**。
    
3. 將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。 您應該使用外部 SIP 網域來設定簡單的 URL，讓外部使用者可以加入會議，例如 `contoso.com` ，外部的 ，而不是 `contoso.local` 內部網域。 因此，SIP 網域應該能夠由外部 DNS 解析。
    
4. 必要時，使用相同步驟編輯 Meet URL。
    
### <a name="to-define-the-optional-admin-simple-url"></a>若要定義選用的 Admin 簡單 URL

1. 在 [拓撲產生器] 中，以滑鼠右鍵按一下 **商務用 Skype Server** 節點，然後按一下 [**編輯屬性]**。
    
2. 在 [**系統管理存取 URL]** 方塊中，輸入您要用於系統管理存取權的簡單 URL 商務用 Skype Server 主控台，然後按一下 [**確定]**。
    
    > [!TIP]
    > 建議您盡可能使用最簡單的 URL 作為 Admin URL。 最簡單的選項是 https://admin 。 _\<domain\>_ 管理員 URL 可以是內部或外部網域，例如 `contoso.local` 或 `contoso.com` ，只要任一記錄可在內部 DNS 中解析即可。 
  
    > [!IMPORTANT]
    > 如果您在初始部署之後變更簡單 URL，則必須留意有哪些變更會影響簡單 URL 的網域名稱系統 (DNS) 記錄和憑證。 如果變更影響簡單 URL 的基底，您也必須變更 DNS 記錄和憑證。 例如，從 `https://sfb.contoso.com/Meet` 變更為 `https://meet.contoso.com` 會從 sfb 變更基底 URL。`contoso.com` 至 `meet.contoso.com` ，因此您必須變更 DNS 記錄和憑證以參考 `meet.contoso.com` 。 如果您將簡單的 URL 從 `https://sfb.contoso.com/Meet` 變更為 `https://sfb.contoso.com/Meetings` ，則 的 `sfb.contoso.com` 基底 URL 會維持不變，因此不需要 DNS 或憑證變更。 不過，每當您變更簡單的 URL 名稱時，就必須在每個 Director 和前端伺服器上執行 **Enable-CsComputer** Cmdlet 來註冊變更。
  
### <a name="publish-and-verify-the-topology"></a>發佈和驗證拓撲

1. 檢查所有簡單 URL 皆已設定正確。
    
2. 確認以SQL Server為基礎的伺服器已上線，且可供安裝拓撲產生器的電腦使用，包括任何必要的防火牆規則。
    
3. 確認檔案共用可供使用，並已定義適當的許可權。
    
4. 確認拓撲中已定義符合部署需求的正確伺服器角色。
    
5. 確認伺服器存在於 Active Directory 網域服務 (AD DS) 中。 當您將伺服器加入網域時，這會自動發生。
    
    當您已驗證拓撲且沒有驗證錯誤時，您應可準備發行拓撲。 如果發生驗證錯誤，您必須先更正這些錯誤，才能發佈拓撲。
    
6. 以滑鼠右鍵按一下 **商務用 Skype Server** 節點，然後按一下 [**發佈拓撲]**。
    
7. 在 **[發行拓撲]** 頁面上，按 **[下一步]**。
    
8. 在 [ **選取中央管理伺服器** ] 頁面上，選取前端集區，如圖所示。
    
    > [!NOTE]
    > 您可以按一下 [ **進階** ] 來設定資料庫檔案位置。
  
     ![選取 [中央管理Microsoft Store伺服器]。](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. 在 [ **選取資料庫]** 頁面上，選取您要發佈的資料庫。
    
    > [!NOTE]
    > 如果您沒有建立資料庫的適當許可權，您可以清除這些資料庫旁邊的核取方塊，且具有適當許可權的人員稍後可以建立資料庫。 如需需求的詳細資訊，請參閱[商務用 Skype Server的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。 
  
10. (選用) 按一下 **[進階]**。 藉由使用進階SQL Server資料檔案放置選項，您可以在下列選項之間進行選取： 
    
    - **自動判斷資料庫檔案位置**- 此選項會根據以SQL Server為基礎的伺服器上的磁片設定，將記錄檔和資料檔案散發到最佳位置，以決定最佳的操作效能。
    
    - **使用SQL Server實例預設** 值 - 此選項會使用 實例設定，將記錄檔和資料檔案放入以SQL Server為基礎的伺服器上。 此選項不使用 SQL Server 型伺服器的運作功能來判斷記錄和資料的最佳位置。 SQL Server 系統管理員通常會將記錄和資料檔案移至對於 SQL Server 型伺服器和組織管理程序而言適合的位置。
    
    依序按一下 **[確定]** 和 **[下一步]**。 
    
11. 選擇性地按一下 [ **進階]**。 藉由使用進階SQL Server資料檔案放置選項，您可以在下列選項之間進行選取： 
    
    - **自動判斷資料庫檔案位置**- 此選項會根據以SQL Server為基礎的伺服器上的磁片設定，將記錄檔和資料檔案散發到最佳位置，以決定最佳的操作效能。
    
    - **使用SQL Server實例預設** 值 - 此選項會使用 實例設定，將記錄檔和資料檔案放入以SQL Server為基礎的伺服器上。 此選項不使用 SQL Server 型伺服器的運作功能來判斷記錄和資料的最佳位置。 SQL Server 系統管理員通常會將記錄和資料檔案移至對於 SQL Server 型伺服器和組織管理程序而言適合的位置。
    
    按一下 **[確定]**。
    
12. 按 **[下一步]** 完成發行程序。
    
    > [!NOTE]
    > 此步驟的常見失敗是無法建立SQL Server資料庫。 當進程無法完成時，會提供錯誤，如圖所示。 最可能的原因是嘗試建立資料庫的使用者沒有適當的許可權，或因為防火牆或其他網路問題而無法連絡SQL Server系統。 
  
     ![建立中央管理存放區時發生錯誤。](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. 發佈程式完成時，您會看到連結來開啟後續步驟的清單。 **按一下 [按一下這裡] 以開啟待辦清單** 以檢視後續步驟，然後按一下 [**完成]**。 
    
    資料庫建立的「已完成且出現警告」訊息並不表示發生錯誤。 安裝程式必須變更SQL Server中的設定，商務用 Skype Server才能正確運作。 當設定在SQL Server中變更時，會記錄為警告，讓SQL Server系統管理員能夠確切瞭解安裝程式已完成的內容。 如果您收到警告，您可以選取記錄，然後按一下 [ **檢視記錄** ] 以檢視警告的詳細資料。
    
    成功發佈拓撲之後，您可以開始在拓撲中執行商務用 Skype Server的每部伺服器上安裝中央管理存放區的本機複本。 建議您從第一個前端集區開始。 
