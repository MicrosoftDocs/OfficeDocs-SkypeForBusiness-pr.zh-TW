---
title: Lync Server 2013：設定自動探索的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e97bb7d77bbd468fff18084ecc7d4da8c5feb7f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502110"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中設定自動探索的憑證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-12_

Director 集區、前端集區及反向 proxy 的憑證，都需要額外的主體替代名稱專案，以支援與 Lync 用戶端的安全連線。

<div>


> [!NOTE]  
> 您可以使用 <STRONG>Get-CsCertificate</STRONG> Cmdlet 來檢視目前指派的憑證相關資訊。 然而，預設檢視會截斷憑證屬性，而且不會顯示 SubjectAlternativeNames 屬性中所有的值。 您可以使用 <STRONG>Get-CsCertificate</STRONG>、<STRONG>Request-</STRONG>CsCertificate 和 <STRONG>Set-CsCertificate</STRONG> Cmdlet 來檢視部分資訊，並要求及指派憑證。 不過，如果您不確定目前憑證上主體替代名稱 (SAN) 的屬性，這並不是最好的方法。 若要查看憑證和所有的屬性成員，建議使用 <EM>Microsoft Management Console (MMC) </EM> 中的 [憑證] 嵌入式管理單元，或使用 Lync Server 部署嚮導。 在 [Lync Server 部署嚮導] 中，您可以使用 [憑證] 嚮導來查看憑證屬性。 下列程式會詳細說明如何使用 Lync Server 管理命令介面和 <EM>Microsoft Management Console (MMC) </EM> 來查看、要求與指派憑證的程式。 若要使用 Lync Server 部署嚮導，請參閱此處的詳細資料：如果您已部署選用的 Director 或 Director 集區： <A href="lync-server-2013-configure-certificates-for-the-director.md">在 Lync Server 2013 中設定 director 的憑證</A>。 若為前端伺服器或前端集區，請參閱以下的詳細資料： <A href="lync-server-2013-configure-certificates-for-servers.md">在 Lync Server 2013 中為伺服器設定憑證</A>。<BR>此程序中的最初步驟是準備步驟，引導您成為目前憑證扮演的角色。 根據預設，憑證不會有 lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain &gt; 或 lyncdiscoverinternal。 &lt;內部功能變數名稱 &gt; 專案，除非您先前已安裝行動服務，或是預先準備好您的憑證。 這個程序使用 SIP 網域名稱範例 ‘contoso.com’ 及內部網域名稱範例  ‘contoso.net’。<BR>Lync Server 2013 和 Lync Server 2010 的預設憑證設定是使用名為 ' Default ) ' 的單一憑證 (，但 web 服務) 、WebServicesExternal 和 WebServicesInternal 以外的目的預設 (。 選用設定是針對每種用途使用不同的憑證。 您可以使用 Lync Server 管理命令介面和 Windows PowerShell Cmdlet 來管理憑證，或使用 Lync Server 部署嚮導中的憑證嚮導來管理憑證。



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>使用 Lync Server 管理命令介面來更新具有新主體替代名稱的憑證

1.  使用具有本機系統管理員權限的帳戶登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  找出哪些憑證已經指派給伺服器，以及使用類型為何。在下一個步驟中，您會需要此資訊來指派更新的憑證。請在命令列中輸入：
    
        Get-CsCertificate

4.  查閱上一個步驟的輸出，看看是否有單一憑證指派至多個用途，或者是否為每個用途指派不同的憑證。查閱 Use 參數，以找出憑證的用法。針對所顯示的憑證比較 Thumbprint 參數，看看相同的憑證是否有多個用途。

5.  更新憑證。在命令列中輸入：
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    例如，如果 **Get-CsCertificate** Cmdlet 顯示一個含有 Use of Default 的憑證、一個含有 Use of WebServicesInternal 的憑證，以及一個含有 Use of WebServicesExternal 的憑證 , 而且它們全都有相同的憑證指紋值，請在命令列中輸入：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要事項：**
    
    如果為每個用途指派不同的憑證 (每個憑證的憑證指紋值都不同)，則切勿以多種類型來執行 **Set-CsCertificate** Cmdlet。 在此情況下，要為每個用途個別執行 **Set-CsCertificate** Cmdlet。 例如：
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  如果要檢視憑證，依序按一下 **[開始]** 和 **[執行…]**。鍵入 MMC 以開啟 Microsoft Management Console。

7.  從 MMC 功能表中，依序選取 **[檔案]**、**[新增/移除嵌入式管理單元…]** 和 [憑證]。按一下 **[新增]**。出現提示時，選取 **[電腦帳戶]**，然後按 **[下一步]**。

8.  如果憑證位於這部電腦上，請選取 [ **本機電腦**]。 如果憑證位於另一台電腦上，則選取 **[另一台電腦]**，鍵入電腦的完整網域名稱或按一下 **[請輸入物件名稱來選取]** 中的 **[瀏覽]**，鍵入電腦的名稱。 按一下 **[檢查名稱]**。 解析出電腦的名稱之後，將會加上底線。 依序按一下 **[確定]** 和 **[完成]**。 按一下 **[確定]** 以認可選取項目，然後關閉 **[新增/移除嵌入式管理單元]** 對話方塊。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果憑證未出現在主控台中，請確定您沒有選取 [使用者或服務]。 您必須選取 [電腦]，否則您將無法找到 probper 憑證。

    
    </div>

9.  如果要檢視憑證的屬性，依序展開 **[憑證]** 和 **[個人]**，然後選取 **[憑證]**。選取要檢視的憑證，用滑鼠右鍵按一下憑證，然後選取 **[開啟]**。

10. 在 **[憑證]** 檢視中，選取 **[詳細資料]**。您可以在此處選取 **[主體]** 來選取憑證主體名稱，隨即顯示指派的主體名稱和相關屬性。

11. 若要查看指派的主體替代名稱，請選取 [ **主體替代名稱**]。 隨即會顯示所有指派的主體替代名稱。 根據預設，在屬性中找到的主體替代名稱是「 **DNS 名稱** 」類型。 若 IPv6 AAAA) 記錄，您應該會看到下列成員 (所有應該是的功能變數名稱（如 DNS 主機中所述） (A 或（如果有的話）：
    
      - 此集區的集區名稱，或單一伺服器名稱 (如果不是集區)
    
      - 被指派憑證的伺服器名稱
    
      - 簡單 URL 記錄，通常為 meet 和 dialin
    
      - Web 服務的內部及 Web 服務外部名稱 (例如，webpool01.contoso.net、webpool01.contoso.com) ，其依據拓撲產生器和透過 ridden Web 服務選取範圍內的選擇。
    
      - 如果已指派，則 lyncdiscover。\<sipdomain\> 和 lyncdiscoverinternal。\<sipdomain\> 記錄。
    
    最後一項是您最感興趣的 – 是否有 lyncdiscover 和 lyncdiscoverinternal SAN 項目。
    
    取得此資訊之後，即可關閉憑證檢視和 MMC。

12. 如果自動探索服務，表示 lyncdiscover。 \>功能變數名稱 \> 和 lyncdiscoverinternal。\<domain name\>  (根據此為外部或內部憑證) 主體替代名稱缺失，且預設使用單一預設憑證、WebServicesInternal 和 WebServiceExternal 類型，請執行下列操作：
    
      - 在 Lync Server 管理命令介面命令列提示字元處，輸入：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有許多 SIP 網域，則無法使用新的 AllSipDomain 參數。 相反地，您必須使用 DomainName 參數。 當您使用 DomainName 參數時，必須定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。 例如：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 如果要指派憑證，請鍵入：
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中 “Thumbprint” 代表對新發行的憑證顯示的指紋。

13. 針對在對 Default、WebServicesInternal 和 WebServicesExternal 使用不同憑證時遺漏的內部自動探索主體替代名稱，請執行下列動作：
    
      - 在 Lync Server 管理命令介面命令列提示字元處，輸入：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有許多 SIP 網域，則不能使用新的 AllSipDomain 參數，而必須使用 DomainName 參數。當您使用 DomainName 參數時，必須為 SIP 網域 FQDN 使用適當的字首。例如：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 針對遺漏的外部自動探索主體替代名稱，在命令列中輸入：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有許多 SIP 網域，則不能使用新的 AllSipDomain 參數，而必須使用 DomainName 參數。當您使用 DomainName 參數時，必須為 SIP 網域 FQDN 使用適當的字首。例如：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 如果要指派個別憑證類型，請鍵入：
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中 “Thumbprint” 代表對新發行的個別憑證顯示的指紋。

</div>

</div>

<span> </span>

</div>

</div>

</div>

