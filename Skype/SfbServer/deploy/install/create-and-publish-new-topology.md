---
title: 在商務用 Skype Server 中建立和發佈新的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 451c41a1-b8c5-4dc3-9e48-0da9ed5381a1
description: '摘要: 瞭解如何在安裝商務用 Skype Server 前建立、發佈及驗證新的拓撲。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server, 網址為: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: c62e2ae061f02f195d0a9560d08234c452543d88
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245006"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>在商務用 Skype Server 中建立和發佈新的拓撲
 
**摘要:** 瞭解如何在安裝商務用 Skype Server 前建立、發佈及驗證新的拓撲。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server, 網址為: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
您必須先建立拓撲併發布, 才能在拓撲中的每個伺服器上安裝商務用 Skype Server 系統。 當您發佈拓撲時, 會將拓撲資訊載入到中央管理儲存資料庫中。 如果這是企業版文件庫, 當您第一次發佈新的拓撲時, 就會建立中央管理儲存資料庫。 如果這是標準版, 您必須先從 [部署嚮導] 執行 [準備第一個標準版伺服器] 程式, 然後才能發佈拓撲。 這是為了準備標準版本, 只要安裝 SQL Server Express Edition 實例並建立中央管理儲存。 您可以依照任何循序執行步驟1到5。 不過, 您必須在順序中執行步驟6、7和 8, 並在步驟1到5之後, 如圖表中所述。 若要瞭解如何建立及發佈新的拓撲, 請參閱8的步驟6。
  
![概覽圖表](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>Create and publish new topology

您可以使用商務用 Skype Server 拓撲產生器來設計、定義、設定及發佈拓撲。 此工具是在本文先前安裝管理工具時安裝的。 建立拓撲時, 有許多不同的選項可供您選擇。 在此程式中, 您將使用會議建立基本拓撲。
  
> [!IMPORTANT]
> 商務用 Skype 伺服器需要 SQL Server 才能運作。 主要資料庫稱為「中央管理」存放區。 如果您要部署企業版, 則會在您使用下列步驟發佈拓撲時建立這些資料庫。 在這種情況下, 拓撲建立器會要求您輸入連線資訊至 SQL Server 的安裝。 如果您打算部署標準版版本, 您必須先安裝 SQL Server Express Edition, 才能定義併發布新的拓撲。 若要安裝 SQL Server Express Edition, 您應該在將充當前端的伺服器上開啟 [部署嚮導], 然後執行 [準備第一個標準版伺服器]。 當您按一下 [準備第一個標準版 Server] 時, [部署嚮導] 會自動安裝 SQL Server Express Edition 並建立中央管理儲存資料庫。 
  
### <a name="create-a-new-topology"></a>建立新的拓撲

1. 以擁有拓撲建立器存取權的標準使用者身分登入。
    
2. 開啟商務用 Skype Server 拓撲建立器。
    
3. 選取 [**新拓撲**], 然後按一下 **[確定]**。
    
4. 選取拓朴設定檔的位置和檔案名。
    
    > [!NOTE]
    > 拓撲配置會儲存為拓撲建立器 XML (tbxml) 檔案。 當您發佈拓撲時, 您會將設定資訊從檔案推送至 SQL Server 資料庫。 當您在未來開啟拓撲建立器時, 您可以將現有的配置從 SQL Server 直接下載到拓撲建立器中, 然後將它發佈回 SQL Server, 或將它儲存為拓撲建立器設定檔。 
  
5. 在 [**定義主要網域] 畫面**上, 輸入**主要 SIP 網域**, 然後按 **[下一步]**。 在這個範例中, 我們使用的是**contoso**, 如圖中所示。
    
     ![定義主要 sip 網域。](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. 新增任何其他支援的 SIP 網域, 然後按 **[下一步]**。
    
7. 輸入第一個網站的**名稱**和**描述**(位置), 然後按一下 **[下一步]**, 如圖所示。
    
     ![定義第一個網站 (位置)。](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. 輸入該網站的**市/縣**、**州/省**及**國家/地區代碼**, 然後按一下 **[下一步]**。
    
9. 按一下 **[完成]** 以完成定義新拓撲的程式。 新的 [前端] 嚮導會自動啟動。
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>定義前端池或標準版伺服器

1. 查看嚮導先決條件, 然後按 **[下一步**]。
    
2. 輸入該池子的完整功能變數名稱 (FQDN), 然後選取 [**企業版前端池**] 或 [**標準版伺服器**], 然後按一下 **[下一步]**, 如圖所示。
    
    > [!TIP]
    > 商務用 Skype Server Enterprise Edition 可以包含多個伺服器共同作業, 以提供前端角色。 當使用多個伺服器來履行角色時, 稱為「池」。 因此, 多個伺服器共同合作來提供前端角色也稱為 [前端] 池。 商務用 Skype Server 標準版只能包含一個伺服器來提供前端角色。 即使只有單一伺服器提供該角色, 一般也會參照前端池。 
  
     ![定義 [前端] 池。](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. 輸入池中所有電腦的完整功能變數名稱 (Fqdn), 然後按一下 [**下一步]** , 如圖中所示。
    
     ![定義池中的電腦。](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. 選取將包含在此拓撲中的功能, 然後按一下 **[下一步]** , 如圖中所示。
    
    > [!NOTE]
    > 商務用 Skype 伺服器包含許多高級功能。 針對您想要使用的每個特定功能, 查看規劃與部署檔。 
  
     ![選取要部署的功能。](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. 在 [**選取 collocated 伺服器角色**] 頁面上, 您可以選擇 collocate 前端伺服器上的中繼伺服器, 或選擇將其部署為獨立伺服器。
    
    如果您想要在企業版前端池中 collocate 轉送伺服器, 請確認已選取此核取方塊。 伺服器角色將會部署在池伺服器上。 如果您想要將中繼伺服器部署為獨立伺服器, 請清除適當的核取方塊。 在您完全部署前端伺服器之後, 您將會在個別的部署步驟中部署轉送伺服器。 如需 collocation 的規劃詳細資料, 請參閱[商務用 Skype Server 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)。
    
6. 透過使用 [**關聯伺服器角色與此前端池**] 頁面, 您可以定義伺服器角色並將其與前端池建立關聯。 下列角色可供使用:
    
    **啟用邊緣池**定義並關聯單一邊緣伺服器或邊緣伺服器池。 Edge 伺服器可協助組織內部使用者與組織外部人員之間的通訊與共同作業, 包括聯盟使用者。
    
    您可以使用兩種可能的案例來部署及關聯伺服器角色。
    
    針對案例 1, 您正在定義新安裝的新拓撲。 您可以採用下列其中一種方法來進行安裝:
    
   - 讓核取方塊保持清除, 然後定義拓撲。 在您已發佈、設定及測試前端與後端伺服器角色之後, 您可以再次執行拓撲建立程式, 以將角色服務器新增到拓撲結構中。 使用此策略, 您可以測試執行 SQL Server 的前端池和伺服器, 而不需要額外的角色進一步複雜。 完成初始測試之後, 您可以再次執行拓撲建立器, 以選取您需要部署的角色。
    
   - 選取您要安裝的角色, 然後設定硬體以適應選取的角色。
    
     若是案例二, 就表示您已有部署, 且您的基礎結構已準備好使用新的角色, 或者您需要將現有角色與新的前端伺服器建立關聯。
    
   - 在這種情況下, 您將會選取您想要部署或與新的前端伺服器建立關聯的角色。 不論是哪一種情況, 您都會繼續定義角色、設定任何所需的硬體, 以及繼續安裝。
    
7. 接下來, 您將定義將與拓撲搭配使用的 SQL Server 存放區。 在這個範例中, 我們使用預設實例。 如需 SQL Server 功能 (例如高可用性) 的詳細資訊, 請參閱[在商務用 Skype Server 中規劃高可用性和災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
    
   - 若要使用已在拓撲中定義的現有 SQL Server store, 請選取 **[SQL store**] 中的實例。
    
   - 若要定義新的 SQL Server 實例來儲存 [池資訊], 請按一下 [**新增**], 然後在 [**定義新的 sql store** ] 對話方塊中指定**SQL Server FQDN** 。
    
   - 若要指定 SQL Server 實例的名稱, 請選取 [**命名實例**], 然後指定實例的名稱。
    
   - 若要使用預設實例, 請按一下 [**預設實例**]。
    
   - 若要使用 SQL 鏡像, 請選取 [**啟用 sql 鏡像**], 然後選取現有的實例, 或建立新的實例。

     > [!NOTE]
     > 在商務用 Skype Server 2015 中提供 SQL 鏡像, 但商務用 Skype Server 2019 已不再支援。 使用商務用 Skype Server 2019 時, AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) 和 SQL 容錯移轉叢集方法都是可取的。
    
     在這個範例中, 我們會輸入**SQL SERVER FQDN**, 並設定任何相關的高可用性設定, 然後按一下 **[確定]**, 如圖中所示。
    
     ![建立 SQL Server 存放區。](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. 決定是否要啟用 SQL Server store 鏡像或 SQL Server 鏡像見證, 然後按 **[下一步]**。
    
9. 定義您要使用的檔案共用。
    
   - 若要使用已在您的拓撲中定義的檔案共用, 請選取 [**使用先前定義**的檔案共用]。
    
   - 若要定義新的檔案共用, 請選取 [**定義新的檔案共用**], 在 [檔案**伺服器 FQDN** ] 方塊中, 輸入檔案共用所在之現有檔案伺服器的 FQDN, 然後在 [檔案**共用**] 方塊中輸入檔案共用的名稱。
    
     在這個範例中, 我們將按一下 [**定義新的檔案存放區**]、輸入 [檔案**伺服器 FQDN** ] 和 [檔案**共用**], 然後按一下 **[下一步]**。
    
     > [!NOTE]
     > 商務用 Skype Server 的檔案共用可以 collocated, 但出於效能考慮, 不建議您這麼做。 請注意, 在這個範例中, 檔案共用已位於將充當檔案共用的單一專用伺服器上。 不過, 我們建議使用其他更健壯的檔案共用系統 (例如使用 Windows Server 2012 R2 的 DFS)。 如需支援的檔案共用系統的詳細資料, 請參閱[商務用 Skype 環境的需求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 如需建立檔案共用的詳細資訊, 請參閱[在商務用 Skype 伺服器中建立檔案共用](create-a-file-share.md)。 您可以定義檔案共用, 但不需要建立檔案共用。 您必須先在您定義的位置中建立檔案共用, 然後才能發佈拓撲。 
  
10. 在 [指定 Web 服務 URL] 頁面上, 您必須決定是否需要覆寫內部 Web 服務池基底 URL。 此覆寫的原因與負載平衡有關。 您可以透過簡單的 DNS 負載平衡來負載平衡基本 SIP 流量。 不過, HTTP/S Web 服務網路流量必須使用支援的硬體或軟體負載平衡方案。 如需支援的負載平衡器, 請參閱[商務用 Skype 的基礎結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。 在這個範例中, 我們使用了 SIP 流量的 DNS 負載平衡, 以及支援的軟體負載平衡方案。 因為我們是以這種方式來分割通信量, 所以我們需要覆寫內部的 Web 服務池 FQDN。 或者, 如果我們有最上層的負載平衡器, 而且透過它傳送所有流量, 而不是使用 SIP 流量的 DNS 負載平衡, 我們就不需要覆寫 Web 服務 URL。 
    
    在本主題的 [DNS] 區段中, 我們為 webint 建立了一個記錄。 這是我們針對 web 服務 HTTP/S 流量所使用的 URL, 而且必須經過我們設定的支援軟體負載平衡器。 因此, 在這個範例中, 我們會覆寫 URL, 讓商務用 Skype 伺服器知道所有的 HTTP/S 流量應該移至 webint, 而不是 pool. 當地, 如圖所示。 如需有關負載平衡的詳細資訊, 請參閱[商務用 Skype 的負載平衡需求](../../plan-your-deployment/network-requirements/load-balancing.md)。
    
    > [!IMPORTANT]
    > 基底 URL 是 URL 的 Web 服務身分識別, 而不是 HTTPs://。 例如, 如果該池的 Web 服務的完整 URL 是https://webint.contoso.local, 則基底 url 是 webint。 
  
    - 如果您正在設定 DNS 負載平衡, 請在這個範例中, 選取 [覆**寫內部 Web 服務池 FQDN** ] 核取方塊, 然後在**內部基礎 url**中輸入內部基本 url (必須與 [池 FQDN] 不同)。 
    
    > [!CAUTION]
    > 如果您決定使用自行定義的 FQDN 來覆寫內部 Web 服務, 則每個 FQDN 都必須是與任何其他前端池、導演或控制器池都是唯一的。 **僅使用標準字元**(包括 A-z、a-z、0-9 和連字號) 當您定義 Url 或完整功能變數名稱時。 請勿使用 Unicode 字元或底線。 外部 DNS 和公用憑證授權單位 (Ca) 通常不支援 URL 或 FQDN 中的非標準字元 (也就是, URL 或 FQDN 必須指派給憑證中的消費者名稱或消費者替換名稱時)。
  
    - 您也可以選擇在**外部基底 url**中輸入外部基底 url。 您可以輸入外部基底 URL, 以將它與您的內部功能變數名稱區分開來。 例如, 您的內部網域是 contoso. 本機, 但是您的外部功能變數名稱是 contoso.com。 您可以使用 contoso.com 功能變數名稱定義 URL, 因為它必須可從公用 DNS 解析。 在反向 proxy 的情況下, 這也很重要。 外部基底 URL 功能變數名稱會與反向 proxy 的 FQDN 功能變數名稱相同。 在行動用戶端上的立即訊息和目前狀態, 必須具備對前端池的 HTTP 存取權。
    
      ![覆寫 web 服務。](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. 如果您在 [**選取功能**] 頁面上選取 [**會議**], 系統會要求您選取 Office Web Apps 伺服器。 按一下 [**新增**] 以開啟對話方塊。
    
12. 在 [**定義新的 Office Web Apps 伺服器**] 對話方塊的 [ **Office WEB apps server FQDN** ] 方塊中, 輸入您的 OFFICE web apps 伺服器 fqdn;當您這樣做時, 您的 Office Web Apps 伺服器探索 URL 應該會自動輸入至 [ **Office Web Apps server 探索 url** ] 方塊中。
    
    如果 Office Web Apps 伺服器已安裝于內部部署, 且在與商務用 Skype Server 相同的網路區域中, 請勿選取 [ **Office Web Apps 伺服器] 部署在外部網路 (也就是 [週邊/網際網路])**。
    
    如果 Office Web Apps 伺服器是在您的內部防火牆外部署, 請選取 [ **Office Web Apps 伺服器] 部署在外部網路 (也就是 [週邊/網際網路])**。
    
13. 按一下 **[完成]** 以完成設定。 如果您在 [**關聯伺服器角色與此前端池**] 頁面上定義其他角色服務器, 則會開啟 [個別角色配置] 嚮導頁面, 您可以在其中設定伺服器角色。 在這個範例中, 我們只選擇 [會議]。
    
### <a name="configure-simple-urls"></a>設定簡單的 Url

1. 在拓撲建立器中, 以滑鼠右鍵按一下**商務用 Skype Server** top 節點, 然後按一下 [**編輯屬性**], 如圖中所示。
    
     ![以滑鼠右鍵按一下 [商務用 Skype 伺服器], 然後選取 [編輯屬性]。](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. 在 [**簡易 url** ] 窗格中, 選取 [**電話存取 url:** (撥入)] 或 [**會議 url:** (見面)] 進行編輯, 然後按一下 [**編輯 URL**]。
    
3. 更新 URL 至您想要的值, 然後按一下 **[確定]** 以儲存編輯的 URL。 您應該使用外部 SIP 網域設定簡單的 URL, 讓外部使用者可以加入會議, 例如 contoso.com (外部), 而不是 contoso. local, 這是內部網域。 因此, SIP 網域應該能夠由外部 DNS 來解析。
    
4. 如有需要, 請使用相同的步驟編輯 [認識 URL]。
    
### <a name="to-define-the-optional-admin-simple-url"></a>定義選用的系統管理員簡易 URL

1. 在拓撲建立器中, 以滑鼠右鍵按一下**商務用 Skype Server**節點, 然後按一下 [**編輯屬性**]。
    
2. 在 [**管理存取 url** ] 方塊中, 輸入您想要的管理存取商務用 Skype Server [控制台] 的簡單 URL, 然後按一下 **[確定]**。
    
    > [!TIP]
    > 我們建議您使用最簡單的管理 URL URL。 最簡單的選項https://admin就是。_ \<網域\>_。 系統管理員 URL 可以是內部或外部網域 (例如 contoso. local 或 contoso.com), 只要任何一種記錄都可在內部 DNS 中解析。 
  
    > [!IMPORTANT]
    > 如果您在初始部署之後變更簡單的 URL, 您必須知道哪些變更會影響您的網域名稱系統 (DNS) 記錄及簡單 Url 的憑證。 如果變更會影響簡單 URL 的基底, 您也必須變更 DNS 記錄和憑證。 例如, 從https://sfb.contoso.com/Meet sfb.contoso.com https://meet.contoso.com變更為 MEET.CONTOSO.COM 的基底 URL, 因此您必須將 DNS 記錄和憑證變更為參照 meet.contoso.com。 如果您將簡單的 URL 改https://sfb.contoso.com/Meet為https://sfb.contoso.com/Meetings[寄件者], 則 SFB.CONTOSO.COM 的基底 url 會保持不變, 因此不需要變更 DNS 或憑證。 不過, 每當您變更簡單的 URL 名稱時, 您必須在每個主管和前端伺服器上執行**Enable-CsComputer** Cmdlet, 才能註冊變更。
  
### <a name="publish-and-verify-the-topology"></a>發佈並驗證拓撲

1. 檢查所有簡單的 Url 是否已正確設定。
    
2. 確認 SQL Server 型伺服器已在線上且可供安裝拓撲產生器的電腦使用, 包括任何必要的防火牆規則。
    
3. 確認檔案共用可用, 且已定義適當的許可權。
    
4. 確認拓撲中定義符合部署需求的正確伺服器角色。
    
5. 確認伺服器已存在於 Active Directory 網域服務 (AD DS) 中。 當您將伺服器加入網域時會自動發生這種情況。
    
    驗證拓朴且沒有驗證錯誤時, 您應該準備好發佈拓撲。 如果有驗證錯誤, 您必須先更正, 才能發佈拓撲。
    
6. 以滑鼠右鍵按一下**商務用 Skype Server**節點, 然後按一下 [**發佈拓撲**]。
    
7. 在 [**發佈拓撲**] 頁面上, 按一下 **[下一步]**。
    
8. 在 [**選取中央管理伺服器**] 頁面上, 選取 [前端] 池, 如圖中所示。
    
    > [!NOTE]
    > 您可以按一下 [**高級**] 來設定資料庫檔案位置。
  
     ![選取 [中央管理商店伺服器]。](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. 在 [**選取資料庫**] 頁面上, 選取您要發佈的資料庫。
    
    > [!NOTE]
    > 如果您沒有建立資料庫的適當許可權, 您可以清除這些資料庫旁邊的核取方塊, 而具有適當許可權的人員就可以在稍後建立資料庫。 如需需求的詳細資訊, 請參閱[商務用 Skype server 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。 
  
10. 您也可以按一下 [**高級**]。 透過使用 [高級 SQL Server 資料檔位置] 選項, 您可以選取下列選項: 
    
    - **自動判斷資料庫檔案位置**: 此選項會將記錄和資料檔案散佈到最佳位置, 以根據您的 SQL server 伺服器上的磁片設定來判斷最佳操作效能。
    
    - **使用 SQL Server 實例預設值**-此選項使用實例設定, 將記錄和資料檔案放到 SQL server 的伺服器。 這個選項不會使用 SQL Server server 伺服器的操作功能來判斷記錄和資料的最佳位置。 SQL Server 系統管理員通常會將記錄和資料檔移至適合 SQL Server 服務器與組織管理程式的位置。
    
    按一下 **[確定]**, 然後按 **[下一步**]。 
    
11. 或者, 按一下 [**高級**]。 透過使用 [高級 SQL Server 資料檔位置] 選項, 您可以選取下列選項: 
    
    - **自動判斷資料庫檔案位置**: 此選項會將記錄和資料檔案散佈到最佳位置, 以根據您的 SQL server 伺服器上的磁片設定來判斷最佳操作效能。
    
    - **使用 SQL Server 實例預設值**-此選項使用實例設定, 將記錄和資料檔案放到 SQL server 的伺服器。 這個選項不會使用 SQL Server server 伺服器的操作功能來判斷記錄和資料的最佳位置。 SQL Server 系統管理員通常會將記錄和資料檔移至適合 SQL Server 服務器與組織管理程式的位置。
    
    按一下 [確定]****。
    
12. 按一下 **[下一步]** 以完成發佈程式。
    
    > [!NOTE]
    > 此步驟的常見失敗是無法建立 SQL Server 資料庫。 當程式無法完成時, 會提供錯誤, 如圖所示。 最可能的原因是, 試圖建立資料庫的使用者沒有適當的許可權, 或由於防火牆或其他網路問題而無法聯絡 SQL Server 系統。 
  
     ![建立中央管理儲存區時發生錯誤。](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. 發佈程式完成後, 您會看到一個連結, 以開啟後續步驟的清單。 按一下 [**按一下這裡以開啟待辦事項清單**] 來查看後續步驟, 然後按一下 **[完成**]。 
    
    資料庫建立的 [完成後的警告] 訊息並不表示發生錯誤。 安裝程式必須在 SQL Server 中變更 [商務用 Skype 伺服器] 的設定, 才能正常運作。 當您在 SQL Server 中變更設定時, 系統會將其記錄為警告, 讓 SQL Server 系統管理員確切瞭解安裝程式已完成的內容。 如果您收到警告, 您可以選取記錄, 然後按一下 [**查看**記錄], 以查看警告的詳細資料。
    
    當拓撲成功發佈之後, 您就可以開始在拓撲中執行商務用 Skype Server 的每台伺服器上安裝中央管理存儲的本機複本。 我們建議您從第一個前端池開始。 
    

