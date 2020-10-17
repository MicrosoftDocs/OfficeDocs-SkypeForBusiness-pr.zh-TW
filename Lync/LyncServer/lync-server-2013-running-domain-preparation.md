---
title: Lync Server 2013：執行網域準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cf14c4b566d6c6447776d3251004f5d508220e3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511110"
---
# <a name="running-domain-preparation-for-lync-server-2013"></a>對 Lync Server 2013 執行網域準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-04-16_

您可以使用安裝程式或 Lync Server 管理命令介面 Cmdlet 來準備網域。 準備網域的 Cmdlet 已 **Enable-CsAdDomain**。

網域準備是準備 Lync Server 2013 的 Active Directory 網域服務的最後一個步驟。

<div>

## <a name="to-use-setup-to-prepare-domains"></a>若要使用安裝程式來準備網域

1.  以 Domain Admins 群組成員的身分登入網域中的任何伺服器。

2.  從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署嚮導。

3.  按一下 **[準備 Active Directory]**，然後等候決定部署狀態。

4.  在 **[步驟 5：準備目前的網域]**，按一下 **[執行]**。

5.  在 [ **準備網域** ] 頁面上，按 **[下一步]**。

6.  在「執行命令」**** 頁面上，尋找 [工作狀態: 已完成]****，然後按一下 [檢視記錄檔]****。

7.  在 [ **動作** ] 欄下，依序展開 [ **網域準備**]、[尋找 **\<Success\>** 執行結果]，以驗證網域準備順利完成，請關閉記錄檔，然後按一下 **[完成]**。

8.  等候 Active Directory 複寫完成，或是強制複寫到樹系根網域控制站之 Active Directory 網站和服務嵌入式管理單元中列出的所有網域控制站。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>若要使用 Cmdlet 準備網域

1.  以 Domain Admins 群組成員的身分登入網域中的任何伺服器。

2.  安裝 Lync Server 核心元件，如下所示：
    
    1.  從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署嚮導。
    
    2.  如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。
    
    3.  [Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。 請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。
    
    4.  在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。 安裝程式會安裝 Lync Server 2013 核心元件。

3.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  運行：
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    例如：
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    如果不指定 Domain 參數，預設值為本機網域。

5.  確認網域準備成功。 運行：
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    例如：
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > GlobalSettingsDomainController 參數可讓您指出通用設定的存放位置。 如果您的設定儲存在系統容器中 (這通常是因為升級部署尚未遷移至設定容器) 中的全域設定，所以您可以在 Active Directory 樹系的根目錄中定義網域控制站。 如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。 如果您未指定此參數，則指令程式會假設設定會儲存在設定容器中，並參照 AD DS 中的任何網域控制站 &nbsp; 。

    
    </div>
    
    如果您未指定 **Domain** 參數，則預設值為本機網域。
    
    如果網域準備成功，則此 Cmdlet 會傳回 **LC \_ DOMAINSETTINGS \_ 狀態 \_ ** 的值。

</div>

<div>

## <a name="see-also"></a>另請參閱


[使用 Cmdlet 進行 Lync Server 2013 的反向網域準備](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[準備 Lync Server 2013 的網域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

