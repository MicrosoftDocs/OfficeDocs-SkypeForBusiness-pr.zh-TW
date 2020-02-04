---
title: Lync Server 2013：修改行動憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>在 Lync Server 2013 中修改行動憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-20_

若要支援 Lync 環境與行動用戶端之間的安全連線，您的控制器池、前臺端池及反向 proxy 的安全通訊端層（SSL）憑證必須更新為其他消費者替換名稱（SAN）專案。 如果您需要瞭解行動性證書需求的詳細資料，請參閱[Lync Server 2013 的行動技術需求](lync-server-2013-technical-requirements-for-mobility.md)中的 [認證需求] 區段，但基本而言，您必須使用隨附的其他 SAN 專案來取得憑證授權單位的新憑證，然後使用本文的步驟新增這些憑證。

當然，在開始之前，通常最好知道您的憑證已有哪些消費者替代名稱。 如果您不確定已設定的內容，有許多方法可讓您瞭解。雖然此選項是執行**CsCertificate**及其他 PowerShell 命令來查看此資訊（我們會在下方逐步引導），但是您可能不會看到您需要的所有屬性。 若要充分瞭解憑證及其所有屬性，您可以移至 Microsoft 管理主控台（MMC）並載入 [憑證] 管理單元（我們也會逐步引導），或者您只需檢查 Lync Server 部署嚮導。

如前所述，下列步驟將逐步引導您使用 Lync Server 管理命令介面和 MMC 更新憑證。 如果您想要改為在 Lync Server 部署嚮導中使用 [憑證] 嚮導，請改為在主管或主管伺服器的 [ [Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) ] 中，核取 [設定認證]。如果您已設定（您可能沒有的話）。 對於前端伺服器或前端池，您會想要[在 Lync Server 2013 中查看伺服器的憑證](lync-server-2013-configure-certificates-for-servers.md)。

需要記住的最後一點是，您可能會在 Lync Server 2013 環境中擁有單一預設憑證，或者您可能會有不同的預設憑證（除了 web 服務以外的所有專案）、WebServicesExternal 和 WebServicesInternal。 無論您是哪一項設定，這些步驟都應該協助您解決。

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>使用 Lync Server 管理命令介面將憑證更新為新的消費者替換名稱

1.  您必須使用擁有本機系統管理員許可權和許可權的帳戶，登入 Lync Server 2013 伺服器。 此外，如果您在步驟12和之後的版本中執行 PowerShell**要求-CsCertificate** ，該帳戶必須擁有指定的憑證頒發機構（CA）的許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  您必須先瞭解已將哪些憑證指派給伺服器，以及使用哪種類型，才能指派更新的憑證。 在命令列中，輸入：
    
        Get-CsCertificate

4.  查看上一個步驟的輸出，以查看是否已將單一憑證指派給多個用途，或是否指派給每個使用不同的憑證。 查看 Use 參數，以瞭解如何使用憑證。 比較所顯示之憑證的指紋參數，以查看相同的憑證是否有多個用途。 在指紋參數上留意您的注意。

5.  更新證書。 在命令列中，輸入：
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    例如，如果**CsCertificate** Cmdlet 顯示使用 [預設值] 的憑證，另一個是使用 WebServicesInternal，而另一個是使用 WebServicesExternal，而另一個則在命令列中有相同的指紋值，您應該輸入：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要事項：**
    
    如果每次使用都指派了個別的憑證（因此，您在上面所核取的指紋值對於每個憑證都不一樣），請務必**不要**執行**CsCertificate** Cmdlet 與多種類型，如上述範例所示。 在這種情況下，請針對每個用途分別執行**CsCertificate** Cmdlet。 例如：
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  若要查看憑證（或憑證），請按一下 [**開始**]，然後按一下 [**執行 ...**]。 輸入 MMC 以開啟 Microsoft 管理主控台。

7.  在 MMC 功能表中，選取 [檔案 **]，選取**[**新增/移除管理單元 ...**]，選取 [憑證]。 按一下 [**新增**]。 出現提示時，請選取 [**電腦帳戶**]，然後按 **[下一步]**。

8.  如果這是憑證所在的伺服器，請選取 [**本機電腦**]。 如果憑證位於另一部電腦上，您應該選取 [**另一台電腦**]，然後您可以輸入電腦的完整功能變數名稱，或按一下 [**流覽]** ，**輸入要選取的物件名稱**，然後輸入電腦的名稱。 按一下 [**檢查名稱**]。 當電腦的名稱解析時，它會加上底線。 按一下 **[確定]**，然後按一下 **[完成]**。 按一下 **[確定]** ，確認選取範圍，然後關閉 [**新增或移除管理單元**] 對話方塊。

9.  若要查看憑證的屬性，請展開 [**憑證**]，展開 [**個人**]，然後選取 [**憑證**]。 選取要查看的憑證，以滑鼠右鍵按一下憑證，然後選取 [**開啟**]。

10. 在 [**憑證**] 視圖中，選取 [**詳細資料**]。 您可以從這裡選取 [ **subject** ]，然後選取 [指派的受領人名稱及相關聯的屬性] 來選取證書受領人名稱。

11. 若要查看指派的主題替換名稱，請選取 [ **Subject 替換名稱**]。 所有指派的主體替換名稱都會顯示在這裡。 此處找到的使用中的 [主題替換名稱] 預設為 [類型**DNS 名稱**]。 您應該會看到下列成員（無論是 DNS 主機（A 或 IPv6 AAAA）記錄中所代表的，都應該是完全限定功能變數名稱：
    
      - 此池的 [池名稱]，如果不是 [池]，則則是單一伺服器名稱
    
      - 證書指派的伺服器名稱
    
      - 簡單的 URL 記錄，通常符合和撥入
    
      - Web 服務內部和 Web 服務外部名稱（例如 webpool01.contoso.net、webpool01.contoso.com），根據拓撲建立器和跨 ridden Web 服務選擇中的選擇進行。
    
      - 如果已指定，則 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄。
    
    最後一個專案是您最感興趣的專案–如果有 lyncdiscover 和 lyncdiscoverinternal 的 SAN 專案。
    
    如果您有多個要檢查的憑證，請重複這些步驟。 有了這些資訊之後，您就可以關閉證書視圖和 MMC。

12. 如果找不到 [自動探索服務消費者] 替換名稱，且您針對預設、WebServicesInternal 和 WebServiceExternal 類型使用單一預設憑證，請執行下列動作：
    
      - 在 Lync Server Management Shell 命令列提示中，鍵入：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。 相反地，您必須使用 DomainName 參數。 當您使用 DomainName 參數時，您必須為 lyncdiscoverinternal 和 lyncdiscover 記錄定義 FQDN。 例如：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 若要指派憑證，請輸入下列內容：
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中，"Thumbprint" 是新頒發的憑證所顯示的指紋。

13. 如果針對預設、WebServicesInternal 和 WebServicesExternal 使用不同的憑證，請執行下列動作，以取得缺少的內部自動探索 SAN：
    
      - 在 Lync Server Management Shell 命令列提示中，鍵入：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。 相反地，您必須使用 DomainName 參數。 當您使用 DomainName 參數時，您必須為 SIP 網域 FQDN 使用適當的首碼。 例如：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 如果缺少外部自動探索消費者替換名稱，請在命令列輸入：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。 相反地，您必須使用 DomainName 參數。 當您使用 DomainName 參數時，您必須為 SIP 網域 FQDN 使用適當的首碼。 例如：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 若要指派個別的憑證類型，請輸入下列內容：
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中，"Thumbprint" 是顯示新頒發的個別憑證的指紋。
    
    <div>
    

    > [!NOTE]  
    > 請注意，只有執行步驟12和13的帳戶才能使用適當的許可權來存取憑證授權單位。 如果您無法以擁有這些許可權的帳戶登入，或者如果您使用的是您憑證的公用或遠端憑證授權單位，您必須透過 Lync Server 部署嚮導要求他們，這會在本文.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

