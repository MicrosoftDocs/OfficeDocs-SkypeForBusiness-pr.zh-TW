---
title: Lync Server 2013： 執行網域準備
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
ms.openlocfilehash: 3d22c35f4e1a2b117ffa765446a94c9a7d2b0fd0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>執行網域準備 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-04-16_

您可以使用安裝程式或 Lync Server 管理命令介面指令程式來準備網域。 準備網域指令程式會**Enable-csaddomain**。

網域準備是準備 Lync Server 2013 的 Active Directory 網域服務的最後一個步驟。

<div>

## <a name="to-use-setup-to-prepare-domains"></a>若要使用安裝程式來準備網域

1.  以 Domain Admins 群組成員的身分登入網域中的任何伺服器。

2.  從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署精靈。

3.  按一下 **[準備 Active Directory]**，然後等候決定部署狀態。

4.  在 **[步驟 5：準備目前的網域]**，按一下 **[執行]**。

5.  在 [**準備網域**] 頁面上，按一下 [**下一步**]。

6.  在「執行命令」**** 頁面上，尋找 [工作狀態: 已完成]****，然後按一下 [檢視記錄檔]****。

7.  在 [**動作**] 欄中，依序展開 [**網域準備**]，並尋找**\<成功\>** 的每一項工作結尾的執行結果，若要確認已順利完成網域準備，關閉記錄檔，然後按一下 [**完成]**。

8.  等候 Active Directory 複寫完成，或是強制複寫到所有網域控制站 [Active Directory 站台及服務] 嵌入式管理單元中樹系根網域控制站列出。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>若要使用 Cmdlet 準備網域

1.  以 Domain Admins 群組成員的身分登入網域中的任何伺服器。

2.  安裝 Lync Server 核心元件，如下所示：
    
    1.  從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署精靈。
    
    2.  如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。
    
    3.  Lync Server 2013 安裝程式] 對話方塊會提示您安裝 Lync Server 檔案的位置。 請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。
    
    4.  在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。 安裝程式會安裝 Lync Server 2013 核心元件。

3.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

4.  執行：
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    例如：
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    如果不指定 Domain 參數，預設值為本機網域。

5.  確認網域準備成功。 執行：
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    例如：
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > GlobalSettingsDomainController 參數可讓您指出通用設定的存放位置。 如果您的設定會儲存在將系統容器 (也就是一般升級部署未有通用設定移轉至組態容器)，在您的 Active Directory 樹系根中定義的網域控制站。 如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。 如果您未指定此參數，指令程式會假設此設定會儲存在 [Configuration] 容器，且所參照的任何網域控制站 AD&nbsp;DS。

    
    </div>
    
    如果您不指定**Domain**參數，預設值為本機網域。
    
    此 cmdlet 會傳回的值為**小寫\_DOMAINSETTINGS\_狀態\_好**如果網域準備是否成功。

</div>

<div>

## <a name="see-also"></a>另請參閱


[使用 cmdlet 來反轉網域準備 Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Lync Server 2013 的準備網域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

