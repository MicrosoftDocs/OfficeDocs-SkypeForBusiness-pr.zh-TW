---
title: Lync Server 2013：設定 XMPP 同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bad6bf4e2b09296e21aec75e206ba867415754a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中設定 XMPP 同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-03_

若要在 Edge 伺服器上部署 XMPP Proxy，您必須針對 XMPP 同盟設定 Edge 伺服器。 若要這樣做，請執行下列步驟。

<div>

## <a name="setting-up-xmpp-federation"></a>設定 XMPP 同盟

1.  登入 Lync Server 部署嚮導以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員的身分安裝的電腦。

2.  在前端伺服器上，開啟 Lync Server 部署嚮導。 按一下 [安裝或更新 Lync Server 系統]，然後按一下 [設定] 或 [移除 Lync Server 元件]。 再次按一下 [執行]。

3.  在安裝程式 Lync Server 元件上，按一下 [下一步]。 [摘要] 畫面會在執行時顯示動作。 完成部署之後，按一下 [查看記錄] 以查看可用的記錄檔。 按一下 [完成] 以完成部署。

4.  在邊緣伺服器上，開啟 Lync Server 部署嚮導。 按一下 [安裝或更新 Lync Server 系統]，然後按一下 [設定] 或 [移除 Lync Server 元件]。 再次按一下 [執行]。

5.  在安裝程式 Lync Server 元件上，按一下 [下一步]。 [摘要] 畫面會在執行時顯示動作。 完成部署之後，按一下 [查看記錄] 以查看可用的記錄檔。 按一下 [完成] 以完成部署。

6.  在 Edge 伺服器的 [部署嚮導] 中，在 [步驟3：要求、安裝或指派憑證] 旁，按一下 [再次執行]。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果您是第一次部署邊緣伺服器，您會看到 [執行]，而不是再次執行。

    
    </div>

7.  在 [可用的憑證工作] 頁面上，按一下 [建立新的憑證要求]。

8.  在 [憑證要求] 頁面上，按一下 [外部邊緣憑證]。

9.  在 [延遲] 或 [立即要求] 頁面上，選取 [立即準備要求，但稍後傳送] 核取方塊。

10. 在 [憑證要求檔案] 頁面上，輸入要儲存申請之檔案的完整路徑和檔案名（例如，c：\\cert\_外部\_edge）。

11. 若要使用預設 Web 文件範本以外的範本，請在 [指定備用憑證範本] 頁面上，選取 [針對所選的憑證授權單位使用替代憑證範本] 核取方塊。

12. 在 [名稱及安全性設定] 頁面上，執行下列動作：
    
    1.  在 [易記名稱] 中，輸入憑證的顯示名稱
    
    2.  在 [位長] 中，指定位長（通常是預設值2048）
    
    3.  確認已選取 [將憑證私人金鑰標示為可匯出] 核取方塊

13. 在 [組織資訊] 頁面上，輸入組織和組織單位的名稱（例如，部門或部門）

14. 在 [地理資訊] 頁面上，指定位置資訊

15. 在 [Subject 名稱/主旨替換名稱] 頁面上，會顯示要由嚮導自動填入的資訊。 如果需要額外的消費者替換名稱，請在接下來的兩個步驟中加以指定。

16. 在 [受領人替代名稱（San）] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\> [主題替換名稱] 清單中的專案。

17. 在 [設定其他消費者替換名稱] 頁面上，指定任何所需的其他消費者替換名稱
    
    <div class=" ">
    

    > [!TIP]  
    > 如果已安裝 XMPP proxy，預設會在 SAN 專案中填入功能變數名稱（例如 [contoso.com]）。 如果您需要更多專案，請在此步驟中加以新增。

    
    </div>

18. 在 [要求摘要] 頁面上，查看要用來產生要求的憑證資訊。

19. 在命令完成執行之後，您可以查看記錄，或按一下 [下一步] 繼續。

20. 在 [憑證要求檔案] 頁面上，您可以按一下 [查看] 或 [結束證書] 嚮導來查看產生的憑證簽署要求（CSR）檔案，方法是按一下 [完成]。

21. 複製要求檔案並提交至您的公用憑證授權單位。

22. 接收、匯入及指派公用憑證之後，您必須停止並重新啟動 Edge 伺服器服務。 您可以在 Lync Server 管理主控台中輸入以下專案來執行此動作：
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. 若要為 XMPP 同盟設定 DNS，您可以將下列 SRV 記錄新增至外部\_DNS： XMPP-伺服器。\_tcp。\<[功能變數名稱] SRV 記錄會解析為邊緣伺服器的存取邊緣 FQDN，埠值為\> 5269。 此外，您還可以設定指向存取邊緣伺服器 IP 位址的 "A" 主機記錄（例如，xmpp.contoso.com）。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 如果您在多個網站中有 Edge 池，我們建議您新增多個 XMPP 同盟的 SRV 記錄。 為組織中的每個 Edge 池新增 SRV 記錄，並為每一個 SRV 記錄指定不同的優先順序。 當所有邊緣池都在執行時，會使用第一個優先順序的邊緣池來處理 XMPP 要求，但如果該 Edge 池向下，您就不需要新增 SRV 記錄，就能重新取得 XMPP 聯盟功能。

    
    </div>

24. 在前端開啟 Lync Server 管理命令介面並輸入以下內容，以設定新的外部存取原則來啟用所有使用者：
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    輸入以下內容來啟用外部使用者的 XMPP 存取：
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. 在部署 XMPP Proxy 的邊緣伺服器上，開啟命令提示字元或 Windows PowerShell™命令列介面，並輸入以下內容：
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    Command **netstat – ano**是 [網路統計] 命令、[參數] **– ano**要求 netstat 顯示所有連線和偵聽埠、位址和埠都以數位形式顯示，且擁有的處理常式識別碼與每個連線相關聯。 字元**|** 會定義管道至下一個命令、[ **findstr**] 或 [尋找字串]。 傳遞給 findstr 的數位5269和23456（作為參數）會指示 findstr 搜尋字串5269和23456的 netstat 輸出。 如果 XMPP 設定正確，命令的結果應該是在外部（埠5269）與 Edge 伺服器的內部（埠23456）介面上，偵聽與建立的連線。
    
    如果命令沒有傳回已建立或在5269和23456上的偵聽埠，請檢查下列專案：

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>疑難排解 XMPP 同盟

1.  若要判斷 XMPP Proxy 是否正在執行，請執行下列動作：

2.  登入執行 XMPP Proxy 服務的邊緣伺服器作為本機管理員群組的成員。

3.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**管理工具**]，按一下 [**服務**]

4.  在 [服務] 中，找出 [Lync Server XMPP 翻譯閘道 Proxy]。 服務應該處於 [**已啟動**] 狀態。 如果沒有啟動，請按一下工具列中的 [**開始**] 圖示。 圖示會顯示為綠色、向右箭號。

5.  確認服務已變更為 [**已啟動**]。 如果它已順利啟動，請關閉 [**服務**] 並繼續。
    
    如果 ther 服務未成功啟動，請從 [管理工具] 開啟事件檢視器，然後參閱 [**應用程式和服務記錄**] 底下的**Lync Server**部分中的錯誤和警告。

6.  在**Lync SERVER XMPP 翻譯閘道**服務執行之後，請重新檢查先前使用的 netstat 命令。 如果您沒有看到已建立或偵聽的會話，請核取並確保在拓撲建立器中正確設定**XMPP 同盟路由**

7.  登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。

8.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

9.  在 [拓撲建立器] 中，選取 XMPP 同盟路由的網站，並檢查以確認**XMPP 同盟**的**網站同盟路由指派**會將您的 Edge 伺服器或 edge 池顯示為所選的 XMPP 同盟路由指派。
    
    如果路線分派不正確或未設定，請以滑鼠右鍵按一下該網站，然後按一下 [**編輯屬性**]。 選取 [XMPP 聯盟] 核取方塊，然後選取正確的 [邊緣伺服器] 或 [Edge] 池。

10. 發佈拓撲。 如需詳細資訊，請參閱[在 Lync Server 2013 中發佈您的拓撲](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > 雖然不需要且通常不必要，您可能會發現您需要重新開機 Edge 伺服器

    
    </div>

11. 使用先前使用的 netstat 程式，確認 Edge 伺服器現在正在接聽，或已在埠5269和埠23456上建立會話。

12. 如果您仍未看到預期的會話，請檢查事件檢視器，找出可能造成通訊問題的原因。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的範例 XMPP 設定 – XMPP 與 Google Talk 的同盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中管理 XMPP 同盟夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

