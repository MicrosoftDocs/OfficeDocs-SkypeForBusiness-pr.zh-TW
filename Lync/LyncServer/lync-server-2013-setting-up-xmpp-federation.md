---
title: Lync Server 2013：設定 XMPP 同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb6b2904ee2a8883c492e570173e73bc001cc03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497520"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中設定 XMPP 同盟

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-03_

如要在 Edge Server 上部署 XMPP Proxy，必須設定 Edge Server 用於 XMPP 同盟。若要這樣做，請執行下列步驟。

<div>

## <a name="setting-up-xmpp-federation"></a>設定 XMPP 同盟

1.  以 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的身分，登入安裝 Lync Server 部署嚮導的電腦。

2.  在前端伺服器上開啟 [Lync Server 部署精靈]。依序按一下 [安裝或更新 Lync Server 系統]、[安裝或移除 Lync Server 元件]、[再執行一次]。

3.  在 [安裝 Lync Server 元件] 中，按 [下一步]。摘要畫面會隨著動作的執行顯示各個動作。部署完成後，按一下 [檢視記錄檔]，檢視可用的記錄檔。按一下 [完成] 完成部署。

4.  在 Edge Server 上開啟 [Lync Server 部署精靈]。依序按一下 [安裝或更新 Lync Server 系統]、[安裝或移除 Lync Server 元件]、[再執行一次]。

5.  在 [安裝 Lync Server 元件] 中，按 [下一步]。摘要畫面會隨著動作的執行顯示各個動作。部署完成後，按一下 [檢視記錄檔]，檢視可用的記錄檔。按一下 [完成] 完成部署。

6.  在 Edge Server 的 [部署精靈] 中，按一下 [步驟 3: 要求、安裝或指派憑證] 旁邊的 [再執行一次]。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果是第一次部署 Edge Server，則會看到 [執行] 而不是 [再執行一次]。

    
    </div>

7.  在 [可用憑證工作] 頁面上，按一下 [建立新憑證要求]。

8.  在 [憑證要求] 頁面上，按一下 [外部邊緣憑證]。

9.  在 [延遲或立即要求] 頁面上，選取 [立即準備此要求，但稍後再傳送] 核取方塊。

10. 在 [憑證要求檔案] 頁面上，輸入要儲存要求的檔案完整路徑和檔案名 (例如，c： \\ cert \_ 外部 \_ edge) 。

11. 若要使用預設 WebServer 範本之外的其他範本，在 [指定其他憑證範本] 頁面上，選取 [針對選取的憑證授權單位使用其他憑證範本] 核取方塊。

12. 在 [名稱和安全性設定] 頁面上，執行下列動作：
    
    1.  在 [易記名稱] 中，輸入憑證的顯示名稱。
    
    2.  在 [位元長度] 中，指定位元長度 (預設值通常是 2048)。
    
    3.  確認已選取 [將憑證私密金鑰標示為可匯出] 核取方塊。

13. 在 [組織資訊] 頁面上，輸入組織的名稱和組織單位 (例如部門)。

14. 在 [地理資訊] 頁面上，指定位置資訊。

15. 在 [主體名稱/主體替代名稱] 頁面上，會顯示精靈將自動填入的資訊。如果您還需要其他主體替代名稱，請在後續兩個步驟中指定。

16. 在 [主體別名 (SANs) ] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\> 專案的主體替代名稱清單。

17. 在 [設定其他主體替代名稱] 頁面上，指定其他任何需要的主體替代名稱。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果已安裝 XMPP Proxy，依照預設會在 SAN 項目中填入網域名稱 (例如 contoso.com)。如需其他項目，請在此步驟中新增。

    
    </div>

18. 在 [要求摘要] 頁面上，檢閱要用來產生要求的憑證資訊。

19. 命令執行完成後，可按一下 [檢視記錄檔] 或按 [下一步] 繼續。

20. 在 [憑證要求檔案] 頁面上，可按一下 [檢視] 以檢視產生的憑證簽署要求 (CSR) 檔案，或按一下 [完成] 結束 [憑證精靈]。

21. 複製要求檔案並提交公用憑證授權單位。

22. 在接收、匯入並指派公用憑證後，必須停止並重新啟動 Edge Server 服務。請在 Lync Server 管理主控台中輸入下列命令：
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. 若要設定 DNS 以進行 XMPP 同盟，您可以將下列 SRV 記錄新增至外部 DNS： \_ XMPP-server。 \_Tcp。\<domain name\> SRV 記錄會解析為 Edge server 的 access edge FQDN，埠值為5269。 此外，您還可以設定「A ' 主機記錄 (例如，xmpp.contoso.com) ，指向 Access Edge Server 的 IP 位址。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 如多個網站中都有 Edge 集區，建議您新增多個 SRV 記錄用於 XMPP 同盟。為組織中每個 Edge 集區新增一個 SRV 記錄，並給予每個 SRV 記錄不同的優先順序。當所有的 Edge 集區都在執行時，XMPP 要求都會由第一優先順序的 Edge 集區來處理，但如果該 Edge 集區發生問題，就不用新增 SRV 記錄來重新取得 XMPP 同盟功能。

    
    </div>

24. 如要設定新的外部存取原則來啟用所有的使用者，請在前端開啟 Lync Server 管理命令介面命令並輸入下列命令：
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    如要啟用外部使用者的 XMPP 存取，請輸入下列命令：
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. 在部署 XMPP Proxy 的 Edge Server 上，開啟命令提示字元或 Windows PowerShell™命令列介面，然後輸入下列命令：
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    **netstat –ano** 命令是網路統計資料命令，參數 **–ano** 會要求 netstat 顯示所有連線及聆聽連接埠 (位址和連接埠以數字格式顯示)，並顯示與每個連線相關的擁有處理程序識別碼。 字元會 **|** 定義管道至下一個命令、 **findstr**或尋找字串。 傳遞給 findstr 做為參數的數位5269和23456，會指示 findstr 搜尋 netstat 的字串5269及23456的輸出。 如果已正確設定 XMPP，則命令的結果應該會產生接聽和建立的連線，這兩種都是在外部 (埠 5269) 和 Edge Server 的內部 (埠 23456) 介面上。
    
    如果命令沒有傳回在 5269 和 23456 建立或聆聽連接埠，請檢查下列事項：

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>疑難排解 XMPP 同盟

1.  如要判斷 XMPP Proxy 是否在執行，請執行下列動作：

2.  以本機系統管理員群組成員的身分，登入執行 XMPP Proxy 服務的 Edge Server。

3.  依序按一下 **[開始]**、**[所有程式]**、**[系統管理工具]** 和 **[服務]**。

4.  在 [服務] 中找到 [Lync Server XMPP 轉譯閘道 Proxy]。該服務應在 **[已啟動]** 狀態。如果不是已啟動，請按一下工具列中的 **[啟動]** 圖示。該圖示顯示為指向右方的綠色箭頭。

5.  確認服務已經變更為 **[已啟動]**。如果服務成功啟動，請關閉 **[服務]** 並繼續。
    
    如果服務未成功啟動，請從 [系統管理工具] 開啟 [事件檢視器]， 然後參考在 **[應用程式及服務記錄檔]** 下 **[Lync Server]** 部分中的錯誤和警告。

6.  一旦 **[Lync Server XMPP 轉譯閘道]** 服務在執行，請重新檢查先前使用的 netstat 命令。 如果您未看到已建立或接聽的會話，請檢查並確定拓撲產生器中已正確設定**XMPP 同盟路由**

7.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

8.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

9.  在 [拓撲產生器] 中，選取 XMPP 同盟路由的網站，並查看以確認**XMPP 同盟**的「**網站同盟路由指派**」會顯示您的 Edge Server 或 edge 集區作為選取的 XMPP 同盟路由指派。
    
    如果路由指派不正確或未設定，請以滑鼠右鍵按一下網站，然後按一下 **[編輯內容]**。 選取 [XMPP 同盟] 核取方塊，然後選取正確的 Edge Server 或 Edge 集區。

10. 發行拓撲。 如需詳細資訊，請參閱 [在 Lync Server 2013 中發行您的拓撲](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > 雖然這不是必要的，通常不需要，但您可能會需要重新開機 Edge Server

    
    </div>

11. 使用先前所用的 netstat 程式，確認 Edge Server 現在正在接聽或已在埠5269和埠23456上建立會話。

12. 如果還是沒看到預期的工作階段，請檢查 [事件檢視器] 中是否有任何可能造成通訊問題的原因。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 的範例 XMPP 設定– XMPP 與 Google 交談的同盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中管理 XMPP 同盟協力廠商](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

