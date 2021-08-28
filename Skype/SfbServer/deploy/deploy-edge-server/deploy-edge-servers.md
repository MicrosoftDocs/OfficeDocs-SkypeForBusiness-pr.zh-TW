---
title: 在商務用 Skype Server 中部署 Edge server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 摘要：瞭解如何將 Edge server 部署到您的商務用 Skype Server 環境中。
ms.openlocfilehash: 611e2e6b4bbc3ef8f1d140b02d8dc3f2bc719953
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623025"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>在商務用 Skype Server 中部署 Edge server
 
**摘要：** 瞭解如何將 Edge server 部署到您的商務用 Skype Server 環境中。
  
下列各節包含的步驟，在[商務用 Skype Server 檔中的 Edge Server 部署商務用 Skype Server 計畫](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)已經過評審之後，將遵循這些步驟。 部署步驟如下：
  
- 網路介面
    
- 安裝
    
- 憑證
    
- 啟動 Edge Server
    
## <a name="network-interfaces"></a>網路介面

如規劃所述，您可以使用主控 Edge Server 的周邊網路中的 DNS，或在周邊網路中未設定 DNS，來設定網路介面。
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>在周邊網路中搭配 DNS 伺服器的介面設定

1. 針對每一部 Edge Server 安裝兩個網路介面卡，一個用於內部對介面，另一個用於外部介面。
    
    > [!NOTE]
    > 內部和外部子網不得彼此路由傳送。 
  
2. 您可以在外部介面上，設定下列 **其中一項** ：
    
   a. 外部周邊網路子網上的三個靜態 IP 位址，並將預設閘道指向外部防火牆的內部介面。 設定配接器的 DNS 設定，使其指向一對周邊 DNS 伺服器。
    
   b. 外部周邊網路子網上的一個靜態 IP 位址，將預設閘道指向外部防火牆的內部介面。 設定配接器的 DNS 設定，使其指向一對周邊 DNS 伺服器。 只有在您先前已設定拓撲在埠指派中具有非標準值時，才可接受此設定，這會在 [[建立您的商務用 Skype Server 文章的 Edge 拓撲](create-your-edge-topology.md)中有所介紹。
    
3. 在您的內部周邊網路子網上，設定一個靜態 IP，但不要設定預設閘道。 設定配接器 DNS 設定，使其指向至少一部 DNS 伺服器，但最好是一對周邊 DNS 伺服器。
    
4. 在內部介面上建立持續性靜態路由，以傳送用戶端、商務用 Skype Server 和 Exchange 整合通訊 (UM) 伺服器所在的所有內部網路。
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>周邊網路中沒有 DNS 伺服器的介面設定

1. 針對每一部 Edge Server 安裝兩個網路介面卡，一個用於內部對介面，另一個用於外部介面。
    
    > [!NOTE]
    > 內部和外部子網不得彼此路由傳送。 
  
2. 您可以在外部介面上，設定下列 **其中一項** ：
    
   a. 外部周邊網路子網上的三個靜態 IP 位址。 您也需要設定外部介面上的預設閘道，例如，將網際網路對向路由器或外部防火牆定義為預設閘道。 設定配接器 DNS 設定以指向外部 DNS 伺服器，理想的是一對外部 DNS 伺服器。
    
   b. 外部周邊網路子網上的一個靜態 IP 位址。 您也需要設定外部介面上的預設閘道，例如，將網際網路對向路由器或外部防火牆定義為預設閘道。 設定配接器 DNS 設定以指向外部 DNS 伺服器，或理想一對外部 DNS 伺服器。 只有在您先前已設定拓撲在埠指派中具有非標準值時，才可接受此設定，這會在 [[建立您的商務用 Skype Server 文章的 Edge 拓撲](create-your-edge-topology.md)中有所介紹。
    
3. 在您的內部周邊網路子網上，設定一個靜態 IP，但不要設定預設閘道。 同時將配接器 DNS 設定保留空白。
    
4. 在內部介面上建立持續性靜態路由，以傳送用戶端、商務用 Skype Server 和 Exchange 整合通訊 (UM) 伺服器所在的所有內部網路。
    
5. 編輯每一部 Edge Server 上的主機檔案，以包含下一個躍點伺服器或虛擬 IP (VIP) 的記錄。 這項記錄會是您在拓撲產生器中設定為 Edge server 下一個躍點位址的 Director、Standard Edition 伺服器或前端集區。 如果您是使用 DNS 負載平衡，請在下一個躍點集區的每個成員中包含一行。
    
## <a name="installation"></a>安裝

若要順利完成這些步驟，您必須遵循為[商務用 Skype Server 文章建立 Edge 拓撲](create-your-edge-topology.md)中的步驟。
  
1. 使用本機系統管理員群組中的帳戶，登入已設定 Edge Server role 的伺服器。
    
2. 您需要在此機器上的 Edge Server 拓撲檔結束時複製您複製的拓撲設定檔。 存取您在 (上放置該設定檔的外部媒體，如 USB 磁片磁碟機或共用) 。
    
3. 啟動 **部署嚮導**。
    
4. 在嚮導開啟之後，按一下 [**安裝或更新商務用 Skype Server 系統**]。
    
5. 嚮導會執行檢查，以查看是否有任何已安裝的專案。 當您第一次執行該嚮導時，您會想要從 **步驟1開始。安裝本機設定存放區。**
    
6. 隨即會出現 [ **設定中央管理存放區的本機複本** ] 對話方塊。 您必須按一下 [ **從檔案匯入] (為 Edge server) 所建議的** 檔案。
    
7. 在這裡，流覽至您先前匯出的拓撲位置，選取 .zip 檔，按一下 [ **開啟**]，然後按 **[下一步]**。
    
8. 部署嚮導會讀取設定檔，並將 XML 設定檔寫入本機電腦。
    
9. **[執行命令]** 程序完成後，按一下 **[完成]**。
    
10. 在 [部署嚮導] 中，按一下 [**步驟 2]。安裝或移除商務用 Skype Server 元件**。 然後，該嚮導將會安裝已儲存在本機電腦上的 XML 設定檔中所指定的商務用 Skype Server Edge 元件。
    
11. 安裝完成後，您可以移至下方的 **憑證** 區段中的步驟。
    
## <a name="certificates"></a>憑證

Edge Server 的憑證需求可在 Edge 憑證規劃檔中找到。 以下是設定憑證的步驟。
  
> [!NOTE]
> 執行憑證嚮導時，您必須以具有您要使用之憑證範本類型之正確許可權的帳戶登入。 根據預設，商務用 Skype Server 憑證要求即將使用網頁伺服器憑證範本。 如果您是以 RTCUniversalServerAdmins 群組成員的帳戶登入，以透過此範本要求憑證，請加倍檢查，確定已將「註冊」許可權指派給群組，以使用該範本。 
  
### <a name="internal-edge-interface-certificates"></a>內部 Edge 介面憑證

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. 下載或匯出 CA 憑證鏈

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp; 單個. 使用 certsrv 網站下載

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。 以本機 Administrators 群組成員的身分，登入您的內部網路中的商務用 Skype Server。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第二。 開啟 [ **開始**] 及 [ **執行** (] 或 [ **搜尋** 並 **執行** ) ]，然後輸入下列專案：
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;例如：
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第三。 在發證 CA 的 certsrv 網頁上，按一下 [ **選取任務**] 底下的 [ **下載 CA 憑證、憑證鏈或 CRL**]。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;四。 在 [ **下載 ca 憑證、憑證鏈或 CRL**] 底下，按一下 [ **下載 ca 憑證鏈**]。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;V。 在 [檔案 **下載** ] 方塊中，按一下 [ **儲存**]。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;六。 將. p7b 檔案儲存至伺服器的硬碟磁碟機上，然後將它複製到每一部 Edge Server 上的資料夾。
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;B。 使用 MMC 匯出

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。 您可以使用 MMC 從任何已加入網域的機器匯出 CA 的根憑證。 移至 [ **開始** ] 和 [ **執行**]，或開啟 [ **搜尋**]，然後輸入 **MMC** 加以開啟。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第二。 在 MMC 主控台中，按一下 [檔案]，**然後按一下 [****新增/移除嵌入式管理單元**]。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第三。 從 [ **新增或移除嵌入式管理單元** ] 對話方塊清單中，選擇 [ **憑證**]，然後按一下 [ **新增**]。 出現提示時，請選取 [ **電腦帳戶**]，然後按 **[下一步]**。 在 [ **選取電腦** ] 對話方塊中，選取 [ **本機電腦**]。 按一下 **[完成]**，然後按一下 **[確定]**。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;四。 展開 [ **憑證 (本機電腦])**。 展開 **[受信任的根憑證授權單位]**。 選取 [ **憑證**]。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;V。 按一下您的 CA 所簽發的根憑證。 以滑鼠右鍵按一下憑證，選擇功能表上的 [ **所有** 工作]，然後選取 [ **匯出**]。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;六。 [ **憑證匯出] 嚮導** 隨即開啟。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;七。 在 [ **匯出檔案格式** ] 對話方塊中，選擇您想要匯出的格式。 建議是 **加密郵件語法 Standard-PKCS #7 憑證 (P7b)**。 如果您也選擇這種方式，請務必同時選取 [ **如果可能的話，包含憑證路徑中的所有憑證** ] 核取方塊，因為這樣也會匯出憑證鏈，包括根 CA 憑證和任何中級憑證。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;八。 在 [ **要匯出的** 檔案] 對話方塊的 [檔案名] 專案中，輸入路徑和檔案名 (預設副檔名為已匯出憑證的 p7b) 。 如果您很容易，請選擇 [ **流覽]** 按鈕，移至您要儲存匯出憑證的位置，然後在這裡命名匯出的憑證。 按一下 [ **儲存**]，然後在 **[下一步]** 準備就緒。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;九。 請複查您的動作摘要，然後按一下 **[完成]** 完成憑證的匯出。 按一下 **[確定]** 確認成功的匯出。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;X。 將. p7b 檔複製到每一部 Edge Server。
    
### <a name="2-import-the-ca-certification-chain"></a>2. 匯入 CA 憑證鏈

&nbsp;&nbsp;&nbsp;單個. 在每一部 Edge Server 上，開啟 MMC (選擇 [ **開始** ] 與 [ **執行**] 或 [ **搜尋**]，然後輸入 **mmc** ，以開啟) 。
    
&nbsp;&nbsp;&nbsp;B。 **在 [檔案**] 功能表上，按一下 [**新增/移除嵌入式管理單元**]，然後選擇 [**新增**]。
    
&nbsp;&nbsp;&nbsp;C。 在 [ **新增或移除嵌入式管理單元** ] 方塊中，按一下 [ **憑證**]，然後按一下 [ **新增**]。
    
&nbsp;&nbsp;&nbsp;D。 在 **[憑證嵌入式管理單元]** 對話方塊中，按一下 **[電腦帳戶]**，然後按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;發送. 在 [ **選取電腦** ] 對話方塊中，確定已選取 [本機電腦] 的 [ **(此主控台執行的電腦)** ] 核取方塊，然後按一下 **[完成]**。
    
&nbsp;&nbsp;&nbsp;F。 按一下 [ **關閉**]，然後按一下 **[確定]**。
    
&nbsp;&nbsp;&nbsp;G。 在主控台樹中，依序展開 [**憑證 (本機電腦])** 中，以滑鼠右鍵按一下 **[信任的根憑證授權** 單位]，移至 [**所有** 工作]，然後按一下 [匯 **入**
    
&nbsp;&nbsp;&nbsp;H。 在出現的嚮導中，在 [ **要匯入** 的檔案] textbox 中指定憑證的檔案名 (您在上一節) 中您所擁有的 p7b 檔案名稱。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;我。 將 [選項按鈕] 保留在 **[將所有憑證放入] 下的存放區中，因為應該選取受信任的根憑證授權單位單位** 。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;J。 查看摘要，然後按一下 **[完成]** 完成匯入。
    
&nbsp;&nbsp;&nbsp;K。 這將需要針對您要部署的每一部 Edge Server 執行。
    
### <a name="3-create-the-certificate-request"></a>3. 建立憑證要求

&nbsp;&nbsp;&nbsp;單個. 登入其中一部 Edge Server，啟動部署嚮導，然後在 [ **步驟3：要求、安裝或指派憑證**] 中，按一下 [ **執行** (**] 或 [** 指派憑證]，如果您已執行此嚮導) 。
    
&nbsp;&nbsp;&nbsp;B。 在 [ **憑證要求** ] 頁面上，確定已選取 [ **內部 Edge 憑證** ]，然後按一下 [ **要求**]。
    
&nbsp;&nbsp;&nbsp;C。 在 [ **延遲或立即要求** ] 頁面上，只要您可以從 Edge 環境存取其中一個，請選擇 [ **立即將要求傳送到線上憑證授權單位** ]，或是 **立即準備此要求，否則請稍後再傳送** 。
    
&nbsp;&nbsp;&nbsp;D。 在 [ **憑證要求** 檔案] 頁面上，輸入檔案儲存位置的完整部分和檔案名 (例如 c:\SkypeInternalEdgeCert.cer) 。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;發送. 在 [ **指定替代的憑證範本** ] 頁面上，若要使用預設 WebServer 範本以外的範本，請選取 [對 **選取的憑證授權單位單位使用其他憑證範本** ] 核取方塊。 否則，不執行任何動作。
    
&nbsp;&nbsp;&nbsp;F。 在 [名稱和安全性設定] 頁面上，執行下列動作：
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   我。 在 [ **易記名稱**] 中，輸入憑證 (的顯示名稱，例如 [內部 Edge) ]。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  第二。 在 [ **位長度**] 中，選擇您的位長度 (預設值為2048，您可以提高安全性，但會使效能降低) 。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  第三。 如果您需要可匯出的憑證，您必須勾選 [將 **憑證私密金鑰標示為可匯出** ] 核取方塊。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  四。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;G。 在 [ **組織資訊** ] 頁面上，輸入組織的名稱和組織單位 (OU) 。 您可以輸入您的部門或部門 (它，例如) 。
    
&nbsp;&nbsp;&nbsp;H。 在 [ **地理資訊** ] 頁面上，輸入您的位置資訊。
    
&nbsp;&nbsp;&nbsp;我。 在 [ **主體名稱/主體替代名稱** ] 頁面上，嚮導應該會自動填入此頁面。
    
&nbsp;&nbsp;&nbsp;J。 在 [ **設定其他主體替代名稱** ] 頁面上，您需要新增任何所需的主體替代名稱。
    
&nbsp;&nbsp;&nbsp;K。 在 [ **要求摘要** ] 頁面上，查看要用來產生要求的憑證資訊。 如果您需要進行變更，請移回並立即執行。
    
&nbsp;&nbsp;&nbsp;我。 然後按 **[下一步]** ，以產生您需要提供給 CA 的 CSR 檔案 (您也可以按一下 [ **查看記錄** 檔] 以查看憑證要求) 的記錄檔。
    
&nbsp;&nbsp;&nbsp;平方米. 在產生要求之後，您可以按一下 [View] （ **查看** ）以查看憑證，然後按一下 **[完成** ] 以關閉視窗。 您必須將 CSR 檔案的內容提供給您的 CA，這樣他們才可以在下一節中為您產生憑證，以匯入此電腦。
    

### <a name="4-import-the-certificate"></a>4. 匯入憑證

&nbsp;&nbsp;&nbsp;單個. 以本機 Administrators 群組成員的身分登入至 Edge Server，而您在上一個程式中提出憑證要求。
    
&nbsp;&nbsp;&nbsp;B。 在 [部署嚮導] 中的 [ **步驟 3] 旁邊。要求、安裝或指派憑證**，請按一下 [ **再執行一次**]。
    
&nbsp;&nbsp;&nbsp;C。 在 [ **可用憑證** 工作] 頁面上，按一下 [匯 **入憑證自 a]。P7b、.pfx 或 .cer** 檔案。
    
&nbsp;&nbsp;&nbsp;D。 在 [匯 **入憑證** ] 頁面上，輸入您在前一節中取得之憑證的完整路徑及檔案名 (，也可以按一下 **[流覽]** ，尋找並選擇) 的檔案。
    
&nbsp;&nbsp;&nbsp;發送. 若要匯入 Edge 集區其他成員的憑證，且憑證包含私密金鑰，請務必選取 [ **包含憑證私密金鑰的憑證** 檔案] 核取方塊，然後指定密碼。 按 **[下一步]** 繼續。
    
&nbsp;&nbsp;&nbsp;F。 在 [**摘要** ] 頁面上，按 **[下一步]** 您已確認資訊，並在成功匯入憑證後 **完成** 。
    
 
### <a name="5-export-the-certificate"></a>5. 匯出憑證

&nbsp;&nbsp;&nbsp;單個. 請確認您已登入已匯入憑證的 Edge Server，成為本機 Administrators 群組的成員。
    
&nbsp;&nbsp;&nbsp;B。 按一下 [ **開始**]、[ **執行** (] 或 [開啟 **搜尋** ) ]，然後輸入 **MMC**。
    
&nbsp;&nbsp;&nbsp;C。 在 MMC 主控台中，按一下 [檔案]，**然後按一下 [****新增/移除嵌入式管理單元**]。
    
&nbsp;&nbsp;&nbsp;D。 在 [ **新增或移除嵌入式管理單元** ] 方塊中，按一下 [ **憑證**]，然後按一下 [ **新增**]。
    
&nbsp;&nbsp;&nbsp;發送. 在 [ **憑證** 嵌入式管理單元] 對話方塊中，選擇 [ **電腦帳戶**]。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;F。 在 [ **選取電腦** ] 對話方塊中，選取 [ **本機電腦： (此主控台執行的電腦])**。 按一下 **[完成]**。 按一下 **[確定]**，然後完成 MMC 主控台的設定。
    
&nbsp;&nbsp;&nbsp;G。 按兩下 [ **憑證 (本機電腦])** 以展開憑證儲存區。 連按兩下 [ **個人**]，然後按一下 [ **憑證**]。
    
  > [!NOTE]
  > 您可能在這裡，而且在本機電腦的憑證個人存放區中看不到任何憑證。 您不需要進行搜尋，如果該機碼不存在，則匯入的憑證沒有相關聯的私密金鑰。 請嘗試一次以上的要求和匯入步驟，如果您確定完全正確，請諮詢 CA 管理員或提供者。 
  
&nbsp;&nbsp;&nbsp;H。 在本機電腦的 [ **憑證個人] 存放區** 中，以滑鼠右鍵按一下您要匯出的憑證。 從產生的功能表中選取 [ **所有** 工作]，然後按一下 [ **匯出**]。
    
&nbsp;&nbsp;&nbsp;我。 在 [憑證匯出精靈] 中，按 [下一步]。 選取 **[是，匯出私密金鑰**]。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;J。 在 [**匯出檔案格式**] 對話方塊中，選取 [**個人資訊] Exchange-PKCS#12 (]。PFX)**，然後選取下列各項：
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   我。 如有可能，請將所有憑證包含在憑證路徑中。
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   第二。 匯出所有延伸屬性。
    
   > [!NOTE]
   > 如果匯出成功，**切勿** 選取 **[刪除私密金鑰**]。 這表示您必須將憑證和私密金鑰重新導入至此 Edge Server。
  
&nbsp;&nbsp;&nbsp;K。 如果您想要指派密碼來保護私密金鑰，您可以輸入私密金鑰的密碼。 重新輸入密碼以加以確認，然後按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;我。 輸入匯出憑證的路徑和檔案名，並使用 **.pfx** 的副檔名。 您必須可以透過集區中的其他 Edge Server 存取該路徑，否則您必須使用外部媒體 (例如 u 盤) ）移動檔案。 作出選擇後，請按 **[下一步]** 。
    
&nbsp;&nbsp;&nbsp;平方米. 在 [ **完成憑證匯出嚮導** ] 對話方塊中查看摘要，然後按一下 **[完成]**。
    
&nbsp;&nbsp;&nbsp;\r\n. 在 [成功匯出] 對話方塊中，按一下 **[確定** ]。
    
 
### <a name="6-assign-the-certificate"></a>6. 指派憑證

&nbsp;&nbsp;&nbsp;單個. 在每一部 Edge Server 上，于 [部署嚮導] 中的 [ **步驟 3] 旁邊。要求、安裝或指派憑證**，請按一下 [ **再執行一次**]。
    
&nbsp;&nbsp;&nbsp;B。 在 [ **可用憑證** 工作] 頁面上，按一下 [ **指派現有的憑證**]。
    
&nbsp;&nbsp;&nbsp;C。 在 [ **憑證指派** ] 頁面上，選取清單中的 [ **Edge Internal** ]。
    
&nbsp;&nbsp;&nbsp;D。 在 [ **憑證存放區** ] 頁面上，選取您為內部 Edge 匯入的憑證，以供先前區段中 () 。
    
&nbsp;&nbsp;&nbsp;發送. 在 [ **憑證指派摘要** ] 頁面上，查看設定，然後按一下 **[下一步]** 指派憑證。
    
&nbsp;&nbsp;&nbsp;F。 在精靈完成頁面中，按一下 **[完成]**。
    
&nbsp;&nbsp;&nbsp;G。 當您完成此程式後，就可以在每一部 Edge Server 上開啟憑證 MMC 嵌入式管理單元，展開 [ **憑證 (本機電腦])**，展開 [ **個人**]，按一下 [ **憑證**]，然後確認 [詳細資料] 窗格中列出的是內部 Edge 憑證。
    
### <a name="external-edge-interface-certificates"></a>外部 Edge 介面憑證

 
### <a name="1-create-the-certificate-request"></a>1. 建立憑證要求

&nbsp;&nbsp;&nbsp;單個. 登入其中一部 Edge Server，啟動部署嚮導，然後在 [ **步驟3：要求、安裝或指派憑證** ] 中，按一下 [執行 (**] 或 [** 指派憑證]，如果您已執行此嚮導) 。
    
&nbsp;&nbsp;&nbsp;B。 在 **[可用憑證工作]** 頁面上，按一下 **[建立新憑證要求]**。
    
&nbsp;&nbsp;&nbsp;C。 在 [ **憑證要求** ] 頁面上，確定已選取 [ **外部邊緣憑證** ]，然後按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;D。 在 [ **延遲或立即要求** ] 頁面上，按一下 **[立即準備此要求，但稍後再傳送**]。
    
&nbsp;&nbsp;&nbsp;發送. 在 [ **憑證要求** 檔案] 頁面上，輸入檔案儲存位置的完整部分和檔案名 (例如 c:\SkypeInternalEdgeCert.cer) 。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;F。 在 [ **指定替代的憑證範本** ] 頁面上，若要使用預設 WebServer 範本以外的範本，請選取 [對 **選取的憑證授權單位單位使用其他憑證範本** ] 核取方塊。
    
&nbsp;&nbsp;&nbsp;G。 在 [名稱和安全性設定] 頁面上，執行下列動作：
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   我。 在 [ **易記名稱**] 中，輸入憑證 (的顯示名稱，例如 [外部 Edge]) 。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  第二。 在 [ **位長度**] 中，選擇您的位長度 (預設值為2048，您可以提高安全性，但會使效能降低) 。
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  第三。 如果您需要可匯出的憑證，您必須勾選 [將 **憑證私密金鑰標示為可匯出** ] 核取方塊。
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 四。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;H。 在 [ **組織資訊** ] 頁面上，輸入組織的名稱和組織單位 (OU) 。 您可以輸入您的部門或部門 (它，例如) 。
    
&nbsp;&nbsp;&nbsp;我。 在 [ **地理資訊** ] 頁面上，輸入您的位置資訊。
    
&nbsp;&nbsp;&nbsp;J。 在 [ **主體名稱/主體替代名稱** ] 頁面上，嚮導應該會自動填入必要的資訊。
    
&nbsp;&nbsp;&nbsp;K。 在 [ **主體別名] 上的 [SIP 網域設定] (SANs)** ] 頁面上，選取 [網域] 核取方塊，以新增 SIP。<sipdomain> 專案的主體替代名稱清單。
    
&nbsp;&nbsp;&nbsp;我。 在 [ **設定其他主體替代名稱** ] 頁面上，您需要新增任何所需的主體替代名稱。
    
&nbsp;&nbsp;&nbsp;平方米. 在 [ **要求摘要** ] 頁面上，查看要用來產生要求的憑證資訊。 如果您需要進行變更，請移回並立即執行。
    
&nbsp;&nbsp;&nbsp;\r\n. 當您準備好時，按 **[下一步]** 以產生您需要提供給 CA 的 CSR 檔案 (您也可以按一下 [ **查看記錄** 檔] 以查看憑證要求) 的記錄檔。
    
&nbsp;&nbsp;&nbsp;複雜度. 在產生要求之後，您可以按一下 [View] （ **查看** ）以查看憑證，然後按一下 **[完成** ] 以關閉視窗。 您必須將 CSR 檔案的內容提供給您的 CA，這樣他們才可以在下一節中為您產生憑證，以匯入此電腦。
    
&nbsp;&nbsp;&nbsp;P。  (選用) 當您提交 CSR 的內容時，系統會要求您提供特定資訊，如下所示 (CAs 會有很大的不同，因此可能不需要這樣做) ：
    
  - **Microsoft** 作為伺服器平臺
    
  - 以 **IIS** 作為版本
    
  - 使用類型的 **網頁伺服器**
    
  - 以回應格式 **PKCS7**
    
 
### <a name="2-import-the-certificate"></a>2. 匯入憑證

&nbsp;&nbsp;&nbsp;單個. 以本機 Administrators 群組成員的身分登入至 Edge Server，而您在上一個程式中提出憑證要求。
    
&nbsp;&nbsp;&nbsp;B。 在 [部署嚮導] 中的 [ **步驟 3] 旁邊。要求、安裝或指派憑證**，請按一下 [ **再執行一次**]。
    
&nbsp;&nbsp;&nbsp;C。 在 [ **可用憑證** 工作] 頁面上，按一下 [匯 **入憑證自 a]。P7b、.pfx 或 .cer** 檔案。
    
&nbsp;&nbsp;&nbsp;D。 在 [匯 **入憑證** ] 頁面上，輸入您在前一節中取得之憑證的完整路徑及檔案名 (，也可以按一下 **[流覽]** ，尋找並選擇) 的檔案。 如果您的憑證包含私密金鑰，請務必選取 [ **憑證檔案包含憑證的私密金鑰**]，然後輸入私密金鑰的密碼。 準備好時，按 **[下一步]** 。
    
&nbsp;&nbsp;&nbsp;發送. 在 [匯 **入憑證摘要** ] 頁面上，複查摘要資訊，然後按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;F。 在 [ **執行命令** ] 頁面上，您可以按一下 [ **查看記錄** 檔]，以複查完成時的匯入結果。 按一下 **[完成]** 以完成憑證匯入。
    
&nbsp;&nbsp;&nbsp;G。 如果您的集區中有其他 Edge Server，您也必須遵循下兩個程式。 如果這是獨立的 Edge Server，就會使用外部憑證完成。
    
 
### <a name="3-export-the-certificate"></a>3. 匯出憑證

&nbsp;&nbsp;&nbsp;單個. 請確認您已登入以本機系統管理員身分匯入憑證的 Edge Server。
    
&nbsp;&nbsp;&nbsp;B。 按一下 [ **開始**]、[ **執行** (] 或 [開啟 **搜尋** ) ]，然後輸入 **MMC**。
    
&nbsp;&nbsp;&nbsp;C。 在 MMC 主控台中，按一下 [檔案]，**然後按一下 [****新增/移除嵌入式管理單元**]。
    
&nbsp;&nbsp;&nbsp;D。 在 [ **新增或移除嵌入式管理單元** ] 方塊中，按一下 [ **憑證**]，然後按一下 [ **新增**]。
    
&nbsp;&nbsp;&nbsp;發送. 在 [ **憑證** 嵌入式管理單元] 對話方塊中，選擇 [ **電腦帳戶**]。 按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;F。 在 [ **選取電腦** ] 對話方塊中，選取 [ **本機電腦： (此主控台執行的電腦])**。 按一下 **[完成]**。 按一下 **[確定]**，然後完成 MMC 主控台的設定。
    
&nbsp;&nbsp;&nbsp;G。 按兩下 [ **憑證 (本機電腦])** 以展開憑證儲存區。 連 **按兩下 [個人**]，然後按一下 [**憑證**]。
    
   > [!NOTE]
   > 您可能在這裡，而且在本機電腦的憑證個人存放區中看不到任何憑證。 您不需要進行搜尋，如果該機碼不存在，則匯入的憑證沒有相關聯的私密金鑰。 請嘗試一次以上的要求和匯入步驟，如果您確定完全正確，請諮詢 CA 管理員或提供者。 
  
&nbsp;&nbsp;&nbsp;H。 在本機電腦的 [ **憑證個人] 存放區** 中，以滑鼠右鍵按一下您要匯出的憑證。 從產生的功能表中 **選取 [所有** 工作]，然後按一下 [**匯出**]。
    
&nbsp;&nbsp;&nbsp;我。 在 [憑證匯出精靈] 中，按 [下一步]。 選取 **[是，匯出私密金鑰**]。 按 **[下一步]**。
    
   > [!NOTE]
   > 如果 **是，請匯出私密金鑰** 不可用，則此憑證的私密金鑰在您取得之前並未標示為匯出。 您必須再次向提供者要求憑證，並在私密金鑰設定為匯出後，才可成功執行這項操作。
  
&nbsp;&nbsp;&nbsp;J。 在 [匯出檔案格式] 對話方塊中，選取 [個人資訊] Exchange-PKCS#12 (]。PFX) 然後選取下列各項：
    
 &nbsp;&nbsp;&nbsp;  我。 如有可能，請將所有憑證包含在憑證路徑中。
    
 &nbsp;&nbsp;&nbsp;  第二。 匯出所有延伸屬性。
    
   > [!NOTE]
   > 如果匯出成功，**切勿** 選取 **[刪除私密金鑰**]。 這表示您必須將憑證和私密金鑰重新導入至此 Edge Server。
  
&nbsp;&nbsp;&nbsp;K。 如果您想要指派密碼來保護私密金鑰，您可以輸入私密金鑰的密碼。 重新輸入密碼以加以確認，然後按 **[下一步]**。
    
&nbsp;&nbsp;&nbsp;我。 輸入匯出憑證的路徑和檔案名，並使用 **.pfx** 的副檔名。 您必須可以透過集區中的其他 Edge Server 存取該路徑，否則您必須使用外部媒體 (例如 u 盤) ）移動檔案。 作出選擇後，請按 **[下一步]** 。
    
&nbsp;&nbsp;&nbsp;平方米. 在 [ **完成憑證匯出嚮導** ] 對話方塊中查看摘要，然後按一下 **[完成]**。
    
&nbsp;&nbsp;&nbsp;\r\n. 在 [成功匯出] 對話方塊中，按一下 **[確定** ]。
    
&nbsp;&nbsp;&nbsp;複雜度. 您現在必須回到此位置之前的 [匯入憑證] 區段，並將憑證匯入至其餘所有 Edge Server，然後繼續進行指派。
    
 
### <a name="4-assign-the-certificate"></a>4. 指派憑證

&nbsp;&nbsp;&nbsp;單個. 在 **每一** 部 Edge Server 上，于 [部署嚮導] 中的 [ **步驟 3] 旁邊。要求、安裝或指派憑證**，請按一下 [ **再執行一次**]。
    
&nbsp;&nbsp;&nbsp;B。 在 [ **可用憑證** 工作] 頁面上，按一下 [ **指派現有的憑證**]。
    
&nbsp;&nbsp;&nbsp;C。 在 [ **憑證指派** ] 頁面上，選取清單中的 [ **Edge External** ]。
    
&nbsp;&nbsp;&nbsp;D。 在 [ **憑證存放區** ] 頁面上，選取您為外部 Edge 匯入的憑證) 上一節所 (。
    
&nbsp;&nbsp;&nbsp;發送. 在 [ **憑證指派摘要** ] 頁面上，查看設定，然後按一下 **[下一步]** 指派憑證。
    
&nbsp;&nbsp;&nbsp;F。 在精靈完成頁面中，按一下 **[完成]**。
    
&nbsp;&nbsp;&nbsp;G。 當您完成此程式後，就可以在每個伺服器上開啟憑證 MMC 嵌入式管理單元，展開 [ **憑證 (本機電腦])**，展開 [ **個人**]，按一下 [ **憑證**]，然後確認 [詳細資料] 窗格中列出的是內部 Edge 憑證。
    
   > [!NOTE]
   > 您也會需要設定反向 proxy 伺服器的憑證。 
  
## <a name="starting-the-edge-servers"></a>啟動 Edge Server

完成安裝後，您需要在部署中的每一部 Edge server 上啟動服務：
  
1. 在每一部 Edge Server 上，于 [ **部署嚮導**] 中的 [ **步驟4：啟動服務**] 旁邊，按一下 [ **執行**]。
    
2. 在 [**開始商務用 Skype Server 服務**] 頁面上，複查服務清單，然後按 **[下一步]** 以啟動服務。
    
3. 啟動服務後，您可以按一下 **[完成** ] 來關閉嚮導。
    
4.  (選用) 仍在 [ **步驟4：啟動服務**] 下，按一下 [ **服務狀態**]。
    
5.  在每一部伺服器上的 [**服務 MMC** ] 中，確認所有的商務用 Skype Server 服務都在執行中。
    

