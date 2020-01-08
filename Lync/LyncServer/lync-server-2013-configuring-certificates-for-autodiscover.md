---
title: Lync Server 2013：針對自動探索設定憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d0270aa76adb7cef2a6da8f6a4f9cb6db090e78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中設定自動探索的憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-12_

您的主管池、前端伺服器池及反向 proxy 的憑證需要額外的消費者替換名稱專案來支援與 Lync 用戶端的安全連線。

<div>


> [!NOTE]  
> 您可以使用<STRONG>CsCertificate</STRONG> Cmdlet 來查看目前指派的憑證的相關資訊。 不過，預設的視圖會截斷憑證的屬性，而不會顯示 SubjectAlternativeNames 屬性中的所有值。 您可以使用<STRONG>CsCertificate</STRONG> 、 <STRONG>Request</STRONG>CsCertificate 和<STRONG>設定 CsCertificate</STRONG> Cmdlet 來查看部分資訊，並要求並指派證書。 不過，如果您不確定目前憑證上的 subject 替換名稱（SAN）屬性，就不是最佳的使用方法。 若要查看憑證及所有屬性成員，建議您使用<EM>Microsoft 管理主控台（MMC）</EM>中的 [憑證] 管理單元，或使用 Lync Server 部署嚮導。 在 Lync Server 部署嚮導中，您可以使用 [憑證] 嚮導來查看憑證屬性。 使用 Lync Server 管理命令介面和<EM>Microsoft 管理主控台（MMC）</EM>來查看、要求及指派憑證的程式在下列程式中詳細說明。 若要使用 Lync Server 部署嚮導，請參閱這裡的詳細資料：如果您已部署選用控制器或控制器池：<A href="lync-server-2013-configure-certificates-for-the-director.md">在 Lync Server 2013 中設定控制器的憑證</A>。 若是前端伺服器或前端池，請參閱這裡的詳細資料：<A href="lync-server-2013-configure-certificates-for-servers.md">在 Lync Server 2013 中設定伺服器的憑證</A>。<BR>此程式中的初始步驟是準備步驟，以指導您瞭解目前證書所扮演的角色。 根據預設，證書將沒有 lyncdiscover。&lt;sipdomain&gt;或 lyncdiscoverinternal。&lt;內部功能變數名稱&gt;專案，除非您先前已安裝過行動服務，或事先已準備好您的憑證。 此程式會使用範例 SIP 功能變數名稱 "contoso.com" 和範例內部功能變數名稱 "contoso.net"。<BR>Lync Server 2013 和 Lync Server 2010 的預設憑證設定是使用單一憑證（名為「預設」）做為預設值（除了 web 服務以外的所有用途）、WebServicesExternal 和 WebServicesInternal。 選擇性設定是針對每個用途使用個別的憑證。 您可以使用 Lync Server 管理命令介面和 Windows PowerShell Cmdlet，或使用 Lync Server 部署嚮導中的 [憑證] 嚮導來管理憑證。



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>使用 Lync Server 管理命令介面將憑證更新為新的消費者替換名稱

1.  使用具有本機系統管理員許可權和許可權的帳戶登入電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  找出已指派給伺服器的憑證和使用的類型。 您必須在下一個步驟中指定此資訊，才能指派已更新的憑證。 在命令列中，輸入：
    
        Get-CsCertificate

4.  查看上一個步驟的輸出，查看是否已指派單一憑證給多個用途，或是否指派給每個使用不同的憑證。 查看 Use 參數，以瞭解如何使用憑證。 比較所顯示之憑證的指紋參數，以查看相同的憑證是否有多個用途。

5.  更新證書。 在命令列中，輸入：
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    例如，如果**CsCertificate** Cmdlet 顯示使用預設值的憑證，另一種是使用 WebServicesInternal，而另一個是使用 WebServicesExternal，而另一個使用，則在命令列中輸入：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要事項：**
    
    如果每次使用都指派了個別的憑證（每個憑證的指紋值不一樣），請務必不要執行**CsCertificate** Cmdlet 與多種類型。 在這種情況下，請針對每個用途分別執行**CsCertificate** Cmdlet。 例如：
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  若要查看憑證，請按一下 [**開始**]，然後按一下 [**執行 ...**]。 輸入 MMC 以開啟 Microsoft 管理主控台。

7.  在 MMC 功能表中，選取 [檔案 **]，選取**[**新增/移除管理單元 ...**]，選取 [憑證]。 按一下 [**新增**]。 出現提示時，請選取 [**電腦帳戶**]，然後按 **[下一步]**。

8.  如果憑證位於這台電腦上，請選取 [**本機電腦**]。 如果憑證位於其他電腦上，請選取 [**另一台電腦**]，輸入電腦的完整功能變數名稱，或按一下 [在**輸入要選取的物件名稱**] 中的 **[流覽]** ，輸入電腦的名稱。 按一下 [**檢查名稱**]。 解析電腦名稱稱時，它會加上底線。 按一下 **[確定]**，然後按一下 **[完成]**。 按一下 **[確定]** ，確認選取範圍，然後關閉 [**新增或移除管理單元**] 對話方塊。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果證書沒有顯示在主控台中，請確定您沒有選取 [使用者或服務]。 您必須選取 [電腦]，否則您將無法找到 probper 憑證。

    
    </div>

9.  若要查看憑證的屬性，請展開 [**憑證**]，展開 [**個人**]，然後選取 [**憑證**]。 選取要查看的憑證，以滑鼠右鍵按一下憑證，然後選取 [**開啟**]。

10. 在 [**憑證**] 視圖中，選取 [**詳細資料**]。 您可以從這裡選取 [ **subject** ]，然後選取 [指派的受領人名稱及相關聯的屬性] 來選取證書受領人名稱。

11. 若要查看指派的主題替換名稱，請選取 [ **Subject 替換名稱**]。 隨即會顯示所有指派的主體替換名稱。 根據預設，在屬性中找到的 [subject 替換名稱] 是「 **DNS 名稱**」。 您應該會看到下列成員（無論是 DNS 主機（A 或 IPv6 AAAA）記錄中所代表的，都應該是完全限定功能變數名稱：
    
      - 此池的 [池名稱]，如果這不是 [池]，則則是單一伺服器名稱
    
      - 證書指派的伺服器名稱
    
      - 簡單的 URL 記錄，通常符合和撥入
    
      - Web 服務內部和 Web 服務外部名稱（例如 webpool01.contoso.net、webpool01.contoso.com），根據拓撲建立器和跨 ridden Web 服務選擇中的選擇進行。
    
      - 如果已指定，則 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄。
    
    最後一個專案是您最感興趣的專案–如果有 lyncdiscover 和 lyncdiscoverinternal 的 SAN 專案。
    
    有了這些資訊之後，您就可以關閉證書視圖和 MMC。

12. 如果自動探索服務，即 lyncdiscover。\>網功能變數名稱稱\>和 lyncdiscoverinternal。\<功能變數名稱\> （根據這是外部或內部憑證）缺少消費者備用名稱，且您針對預設、WebServicesInternal 和 WebServiceExternal 類型使用單一預設憑證，請執行下列動作：
    
      - 在 Lync Server Management Shell 命令列提示中，鍵入：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。 相反地，您必須使用 DomainName 參數。 當您使用 DomainName 參數時，您必須為 lyncdiscoverinternal 和 lyncdiscover 記錄定義 FQDN。 例如：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 若要指派憑證，請輸入下列內容：
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中，"Thumbprint" 是新頒發的憑證所顯示的指紋。

13. 如果針對預設、WebServicesInternal 和 WebServicesExternal 使用不同的憑證時，缺少內部自動探索消費者備用名稱，請執行下列動作：
    
      - 在 Lync Server Management Shell 命令列提示中，鍵入：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。 相反地，您必須使用 DomainName 參數。 當您使用 DomainName 參數時，必須針對 SIP 網域 FQDN 使用適當的首碼。 例如：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 如果缺少外部自動探索消費者替換名稱，請在命令列輸入：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。 相反地，您必須使用 DomainName 參數。 當您使用 DomainName 參數時，必須針對 SIP 網域 FQDN 使用適當的首碼。 例如：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 若要指派個別的憑證類型，請輸入下列內容：
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中，"Thumbprint" 是顯示新頒發的個別憑證的指紋。

</div>

</div>

<span> </span>

</div>

</div>

</div>

