---
title: Lync Server 2013：設定單一內部集區的 web 發佈規則
description: Lync Server 2013：設定單一內部集區的 web 發佈規則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45015c90fdac92fb488affc871f2cfaf9d7506a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560509"
---
# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>在 Lync Server 2013 中設定單一內部集區的 web 發佈規則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-07-07_

Microsoft Forefront 威脅管理閘道2010和 Internet Information Server 應用程式要求路由 (IIS ARR) 使用網頁發行規則，將內部資源（如會議 URL）發佈至網際網路上的使用者。

除了虛擬目錄的 Web 服務 URLs 之外，您還必須針對簡易 URLs、LyncDiscover URL 和 Office Web Apps Server 建立發佈規則。 針對每個簡單 URL，您必須在反向 proxy 上建立一個指向該簡易 URL 的個別規則。

若要部署行動性並使用自動探索，您需要為外部自動探索服務 URL 建立發佈規則。 自動探索也需要適用于 Director 集區和前端集區之外部 Lync Server Web 服務 URL 的發行規則。 如需建立自動探索之網頁發行規則的詳細資訊，請參閱 [在 Lync Server 2013 中設定行動的反向 proxy](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)。

請使用下列程式建立 web 發佈規則。

<div>


> [!NOTE]  
> 這些程式假設您已安裝 Standard Edition 的 Forefront 威脅管理閘道 (TMG) 2010 或已安裝及設定具有應用程式要求路由 (IIS ARR) 擴充的 Internet Information Server。 您使用的是 TMG 或 IIS ARR。



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>在執行 TMG 2010 的電腦上建立網頁伺服器發行規則

1.  依序按一下 [ **開始**]、[ **程式**] 和 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront tmg 管理**]。

2.  在左窗格中，展開 [ **ServerName**]，以滑鼠右鍵按一下 [ **防火牆原則**]，然後選取 [ **新增**]，然後按一下 [網站 **發行規則**]。

3.  在 [ **歡迎使用新增網頁發行規則** ] 頁面上，輸入發行規則 (的顯示名稱，例如，LyncServerWebDownloadsRule) 。

4.  在 [選取規則動作]**** 頁面上，按一下 [允許]****。

5.  在 [發行類型]**** 頁面上，選取 [發行單一網站或負載平衡器]****。

6.  在 [伺服器連線安全性]**** 頁面上，選取 [使用 SSL 連線到發行的 Web 伺服器或伺服器陣列]****。

7.  在 [ **內部發行詳細資料** ] 頁面的 [內部 **網站名稱** ] 方塊中，輸入主控會議內容和通訊錄內容之內部網頁伺服器陣列的完整功能變數名稱 (FQDN) 。
    
    <div>
    

    > [!NOTE]  
    > 如果您的內部伺服器為 Standard Edition server，則此 FQDN 為 Standard Edition server FQDN。 如果您的內部伺服器是前端集區，則此 FQDN 是硬體負載平衡器虛擬 IP (VIP) 負載平衡內部網頁伺服器陣列伺服器。 TMG 伺服器必須能夠將 FQDN 解析為內部網頁伺服器的 IP 位址。 如果 TMG 伺服器無法將 FQDN 解析為正確的 IP 位址，您可以選取 <STRONG>[使用電腦名稱稱或 ip 位址連線到已發佈的伺服器]</STRONG>，然後在 [ <STRONG>電腦名稱稱或</STRONG> <STRONG>ip 位址</STRONG> ] 方塊中，輸入內部網頁伺服器的 IP 位址。 如果您這麼做，您必須確定 TMG 伺服器上的埠53已開啟，而且可以到達位於周邊網路中的 DNS 伺服器。 您也可以使用本機主機檔案中的專案，以提供名稱解析。

    
    </div>

8.  在 [ **內部發行詳細資料** ] 頁面的 [ **路徑 (選用) ** ] 方塊中，輸入 **/\*** 要發佈之資料夾的路徑。
    
    <div>
    

    > [!NOTE]  
    > 在 [網站發佈嚮導] 中，您只能指定一個路徑。 您可以修改規則的屬性，以新增其他路徑。

    
    </div>

9.  在 [**公用名稱詳細資料**] 頁面上，確認已選取 [**接受要求**] 下的 [**功能變數名稱**]，在 [**公用名稱**] 方塊中輸入 [外部 Web 服務 FQDN]。

10. 在 [ **選取 Web** 接聽程式] 頁面上，按一下 [ **新增** ] 以開啟 [新增網頁接聽程式定義] 嚮導。

11. 在 [ **歡迎使用新增網頁接聽程式] 嚮導** 頁面上，于 [網頁接聽程式 **名稱** ] 方塊中輸入 [網頁接聽程式] 的名稱 (例如，LyncServerWebServers) ]。

12. 在 [ **用戶端連線安全性** ] 頁面上，選取 [ **需要與用戶端建立 SSL 安全**連線]。

13. 在 [ **網頁接聽程式 IP 位址]** 頁面上，選取 [ **外部**]，然後按一下 [ **選取 IP 位址**]。

14. 在 [ **外部攔截器 IP 選擇]** 頁面上，選取 **所選網路中 Forefront TMG 電腦上的 [指定的 ip 位址**]，然後選取適當的 ip 位址，按一下 [ **新增**]。

15. 在 [接聽程式 **SSL 憑證]** 頁面上，選取 [ **指派每個 IP 位址的憑證**]，然後選取與外部 web FQDN 相關聯的 IP 位址，然後按一下 [ **選取憑證**]。

16. 在 [ **選取憑證** ] 頁面上，選取符合步驟9中指定之公用名稱的憑證，然後按一下 [ **選取**]。

17. 在 [ **驗證設定** ] 頁面上，選取 [ **無驗證**]。

18. 在 [ **單一登入設定** ] 頁面上，按 **[下一步]**。

19. 在 [ **完成網頁監聽器] 嚮導** 頁面上，確認 [ **網頁** 接聽程式] 設定正確，然後按一下 **[完成]**。

20. 在 [驗證委派]**** 頁面上選取 [沒有委派，但用戶端可以直接驗證]****。

21. 在 [ **使用者組** ] 頁面上，按 **[下一步]**。

22. 在 [正在完成新網頁發行規則精靈]**** 頁面上，確認網頁發行規則設定正確，然後按一下 [完成]****。

23. 按一下詳細資料窗格中的 **[套用]**，以儲存變更並更新設定。

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>在執行 IIS ARR 的電腦上建立網頁伺服器發行規則

1.  將您要用於反向 proxy 的憑證系結到 HTTPS 通訊協定。 依序按一下 [ **開始**]、[ **程式**]、[系統 **管理工具**]，然後按一下 [ **網際網路資訊服務 (IIS) 管理員**]。
    
    <div>
    

    > [!NOTE]  
    > 在 <A href="https://go.microsoft.com/fwlink/?linkid=293391">使用 IIS arr 做為 Lync Server 2013 的反向 Proxy</A>的 NextHop 文章中，可以找到有關部署及設定 IIS arr 的其他協助資訊、螢幕擷取畫面和指導方針。

    
    </div>

2.  若尚未匯入您要用於反向 proxy 的憑證，請將其匯入。 在 [ **Internet Information Services (IIS) 管理員**] 中，按一下主控台左側大小的反向 proxy 伺服器名稱。 在 [ **IIS** ] 底下的 [主控台] 中，尋找 [ **伺服器憑證**]。 以滑鼠右鍵按一下 [ **伺服器憑證** ]，然後選取 [ **開啟功能**]。

3.  在主控台的右側，按一下 [匯 **入 ...**]。 輸入副檔名的路徑和檔案名，或按一下 [ **...** ]。 以流覽憑證。 選取憑證，然後按一下 [ **開啟**]。 在匯出憑證和私密金鑰) 時，提供用來保護私密金鑰 (的密碼。 按一下 [確定]****。 如果已成功匯入憑證，則憑證會顯示為主控台中間的專案，成為 **伺服器憑證**中的專案。

4.  指派供 HTTPS 使用的憑證。 在主控台的左側，選取 IIS 伺服器的 **預設** 網站。 在右側，按一下 [系結 **...**]。 在 [ **網站** 系結] 對話方塊中，按一下 [ **新增 ...**]。 在 [**類型：**] 底下的 [**新增網站**系結] 對話方塊中，選取 [ **HTTPs**]。 選取 [HTTPs] 可讓您選取要用於 HTTPs 的憑證。 在 [ **SSL 憑證：**] 底下，選取您為反向 proxy 匯入的憑證。 按一下 [確定]****。 然後按一下 [ **關閉**]。 現在，該憑證會系結至安全通訊端層的反向 proxy (SSL) 和傳輸層安全性 (TLS) 。
    
    <div>
    

    > [!IMPORTANT]  
    > [！注意] 如果您在關閉「系結憑證遺失的系結」對話方塊時收到警告，您必須尋找並匯入公用 CA 根授權憑證和任何中間 CA 憑證。 請參閱您要求憑證的公用 CA 上的指示，並遵循指示要求和匯入憑證鏈。 如果您從 Edge Server 匯出憑證，您可以匯出根 CA 憑證，以及與 Edge Server 關聯的任何中間 CA 憑證。 將根 CA 憑證匯入電腦的 (，不會與使用者存放區) 受信任的根憑證授權單位儲存區和中級憑證，加入電腦的「中級憑證授權單位」存放區。

    
    </div>

5.  在 [IIS 伺服器名稱] 底下的主控台左側，以滑鼠右鍵按一下 [ **伺服器** 陣列]，然後按一下 [ **建立伺服器陣列 ...**]。
    
    <div>
    

    > [!NOTE]  
    > 如果您沒有看到 [ <STRONG>伺服器</STRONG> 陣列] 節點，您必須安裝應用程式要求路由。 如需詳細資訊，請參閱 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">設定 Lync Server 2013 的反向 proxy 伺服器</A>。

    
    </div>
    
    在 [伺服器陣列中的 **建立伺服器** 陣列] 對話方塊的 [ **伺服器陣列名稱稱**] 中，輸入名稱 (此名稱可以是識別目的的易記名稱) 第一個 URL。 按 **[下一步]**。

6.  在 [**伺服器位址**] 中的 [**新增伺服器**] 對話方塊中，輸入前端伺服器上的外部 web 服務的完整功能變數名稱 (FQDN) 。 在這裡用來做為範例用途的名稱，與在 [Lync Server 2013 中的反向 proxy、憑證摘要-反向 proxy](lync-server-2013-certificate-summary-reverse-proxy.md)的規劃區段中使用的名稱相同。 參照反向 proxy 的規劃，我們輸入 FQDN `webext.contoso.com` 。 確認已選取 [ **線上** ] 旁邊的核取方塊。 按一下 [ **新增** ]，將伺服器新增至此設定之網頁伺服器的集區。
    
    <div>
    

    > [!WARNING]  
    > Lync Server 使用硬體負載平衡器來集區 Director 和前端伺服器以進行 HTTP 及 HTTPS 流量。 將伺服器新增至 IIS ARR 伺服器陣列時，您只會提供一個 FQDN。 FQDN 會是非集區伺服器設定中的前端伺服器或 Director，或為伺服器集區設定的硬體負載平衡器的 FQDN。 使用硬體負載平衡器時，唯一支援的負載平衡 HTTP 和 HTTPS 流量的方法是使用硬體負載平衡器。

    
    </div>

7.  在 [ **新增伺服器** ] 對話方塊中，按一下 [ **高級設定 ...**]。 這會開啟對話方塊，為設定的 FQDN 定義要求的應用程式要求路由。 目的是在 IIS ARR 處理要求時，重新定義所使用的埠。
    
    根據預設，目的地 HTTP 埠必須定義為8080。 按一下目前 **HTTPPort 80** 的 [下一步]，然後將值設為 **8080**。 按一下目前 **HTTPsPort 443** 的 [下一步]，然後將值設為 **4443**。 在100保留 **加權** 參數。 如有需要，您可以在有基線統計資料之後重新定義指定規則的權重。 按一下 **[完成]** 以完成規則設定的此部分。

8.  您可能會看到對話方塊重寫規則，通知您 IIS 管理員可以建立 URL 重新寫入規則，以自動將所有傳入要求路由傳送至伺服器陣列。 按一下 [是]****。 您將會手動調整規則，但是選取 [是] 會設定初始設定。

9.  按一下剛才建立的伺服器陣列名稱稱。 在 [IIS 管理員功能] 視圖中的 [ **伺服器** 陣列] 底下 **，按兩下 [** 快取]。 取消選取 [ **啟用磁碟快取**]。 按一下 **右側的 [** 套用]。

10. 按一下伺服器陣列的名稱。 在 [IIS 管理員功能] 視圖中的 [ **伺服器** 陣列] 底下，按兩下 [ **Proxy**]。 在 [Proxy 設定] 頁面上，將 **超時 (秒) ** 的值變更為適合您部署的值。 按一下 **[** 套用] 以儲存變更。
    
    <div>
    

    > [!IMPORTANT]  
    > Proxy 超時值是一個數位，會因部署而異。 您應該監視您的部署，並修改用戶端的最佳體驗值。 您可以將值設為低200。 如果您在環境中支援 Lync 行動用戶端，則應該將值設為960，以允許來自 Office 365 的推播通知超時，其超時值為900。 您很可能會需要增加超時值，以避免用戶端在用戶端中斷連線後，如果透過 proxy 的連線不會中斷連線，則中斷用戶端的連線。 監視和基本對齊您環境的情況是唯一可以判斷此值的正確設定位置的唯一準確方式。

    
    </div>

11. 按一下伺服器陣列的名稱。 在 [IIS 管理員功能] 視圖中的 [ **伺服器** 陣列] 底下，按兩下 [ **路由規則**]。 在 [路由規則] 下的 [路由規則] 對話方塊中，清除 [啟用 SSL 卸載] 旁邊的核取方塊。 如果無法使用清除核取方塊的功能，請選取 [使用 URL 重新寫入] 核取方塊以 **檢查傳入的要求**。 按一下 **[** 套用] 以儲存變更。
    
    <div>
    

    > [!WARNING]  
    > 反向 proxy 不支援進行 SSL 卸載。

    
    </div>

12. 針對必須透過反向 proxy 傳遞的每個 URL，重複步驟5-11。 常見的清單如下：
    
      - 前端伺服器 Web 服務外部： webext.contoso.com (已透過初始逐步進行設定) 
    
      - Director： webdirext.contoso.com 的外部 Web 服務 director： (選用若要部署 Director) 
    
      - 簡易 URL 符合： meet.contoso.com
    
      - 簡單 URL 撥入： dialin.contoso.com
    
      - Lync 自動探索 URL: lyncdiscover.contoso.com
    
      - Office Web Apps Server URL: officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > Office Web Apps Server 的 URL 會使用不同的 HTTPsPort 位址。 在步驟7中，您將 <STRONG>HTTPsPort</STRONG> 定義為 <STRONG>443</STRONG> ，將 <STRONG>HTTPPort</STRONG> 定義為埠 <STRONG>80</STRONG>。 所有其他設定設定都相同。

        
        </div>

13. 在主控台左側，按一下 IIS 伺服器名稱。 在主控台中央，找到 [ **IIS**] 底下的 [ **URL 重新寫入**]。 按兩下 [URL 重新寫入]，以開啟 URL 重新寫入規則設定。 您應該會看到您在先前步驟中建立的每個伺服器陣列的規則。 否則，請確認您已在 [網際網路資訊伺服器管理員] 主控台中，在 [**起始頁面**] 節點底下緊接著按一下**IIS 伺服器**名稱。

14. 在 [ **URL 重新寫入** ] 對話方塊中，使用 webext.contoso.com 做為範例，顯示的完整的規則名稱是 **ARR \_ webext.contoso.com \_ loadbalance \_ SSL**。
    
      - 按兩下規則以開啟 [ **編輯輸入規則** ] 對話方塊。
    
      - 按一下 [**新增 ...** ] 在 [ **條件** ] 對話方塊中。
    
      - 在 [**條件輸入：** 輸入 **{HTTP \_ 主機}**] 中的**Add 條件**。  (當您輸入時，會出現一個對話方塊，讓您選取條件) 。 在 [ **檢查輸入字串：** ] 下 **，選取 [符合模式**]。 在 **模式輸入** 類型中 **\*** 。 應該選取 [**忽略案例**]。 按一下 [確定]****。
    
      - 在 [ **編輯輸入規則** ] 對話方塊中向內移動，以找出 [ **動作** ] 對話方塊。 **動作類型：** 應該設定為 **路由傳送到伺服器**陣列， **配置：** 設定為 **HTTPs://**， **伺服器陣列：** 設定為套用此規則的 URL。 在此範例中，此範例應設定為 **webext.contoso.com**。 **路徑：** 設定為 **/{R： 0}**
    
      - 按一下 **[** 套用] 以儲存變更。 按一下 [ **回到規則** ] 以回到 URL 重新寫入規則。

15. 針對您所定義的每個 SSL 修正規則（每一個伺服器陣列 URL），重複步驟14中所定義的程式。
    
    <div>
    

    > [!WARNING]  
    > 根據預設，會同時建立 HTTP 規則，並以類似于 SSL 規則的命名來表示。 針對目前的範例，HTTP 規則會命名為 <STRONG>ARR_webext .com _loadbalance</STRONG>。 不需要修改這些規則，而且可以放心地忽略。

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>在 TMG 2010 中修改 web 發行規則的屬性

1.  按一下 [ **開始**]，指向 [ **程式**]，選取 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront tmg 管理**]。

2.  在左窗格中，展開 [ **ServerName**]，然後按一下 [ **防火牆原則**]。

3.  在 [詳細資料] 窗格中，以滑鼠右鍵按一下您在先前程式中建立的網頁伺服器發行規則 (例如，LyncServerExternalRule) ]，然後按一下 [ **屬性**]。

4.  在 [ **屬性** ] 頁面上的 [ **從** ] 索引標籤上，執行下列動作：
    
      - 在 [ **此規則套用至這些來源的流量** ] 清單中，按一下 [ **隨處**]，然後按一下 [ **移除**]。
    
      - 按一下 **[新增]**。
    
      - 在 [ **新增網路實體**] 中，展開 [ **網路**]，按一下 [ **外部**]，按一下 [ **新增**]，然後按一下 [ **關閉**]

5.  在 [ **到** ] 索引標籤上，確定已選取 [ **轉寄原始主機標頭，而非實際的主機標頭** ] 核取方塊。

6.  在 [ **橋接** ] 索引標籤上，選取 [將 **要求重新導向至 SSL 埠** ] 核取方塊，然後指定埠 **4443**。

7.  在 [ **公用名稱** ] 索引標籤上，新增簡易 URLs (例如，meet.contoso.com 和 dialin.contoso.com) 。

8.  按一下 [套用] 以儲存變更， **然後按一下** **[確定]**。

9.  按一下詳細資料窗格中的 **[套用]**，以儲存變更並更新設定。

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>在 IIS ARR 中修改 web 發行規則的屬性

1.  依序按一下 [ **開始**]、[ **程式**]、[系統 **管理工具**]，然後按一下 [ **網際網路資訊服務 (IIS) 管理員**]。

2.  在主控台左側，按一下 IIS 伺服器名稱。

3.  在主控台中央，找到 [ **IIS**] 底下的 [ **URL 重新寫入**]。 按兩下 [URL 重新寫入]，以開啟 URL 重新寫入規則設定。

4.  按兩下您需要修改的規則。 視需要在 **符合 URL**、 **條件**、 **伺服器變數** 或 **動作**時進行修改。

5.  按一下 **[** 套用] 以認可您的變更。 按一下 [ **回到規則** ] 修改其他規則，如果您已完成變更，請關閉 [ **IIS 管理員** ] 主控台。

</div>

</div>

<span> </span>

</div>

</div>

</div>

