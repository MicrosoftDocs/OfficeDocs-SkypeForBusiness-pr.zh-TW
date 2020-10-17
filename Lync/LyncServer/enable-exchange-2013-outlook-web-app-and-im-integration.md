---
title: 啟用 Exchange 2013 Outlook Web App 與 IM 整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da6866565df12ff4484124836f9164d2bf8c35c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502880"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>啟用 Exchange 2013 Outlook Web App 與 IM 整合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

若要啟用 Exchange 2013 Outlook Web Access (OWA) 和立即訊息 (IM) 與 Lync Server 2013 整合，您必須將 Exchange 2013 Client Access Server (CAS) Server 新增至 Lync Server 2013 拓撲，做為信任的應用程式伺服器。

<div>

## <a name="to-create-a-trusted-application-pool"></a>建立信任的應用程式集區

1.  啟動 Lync Server 2013 管理命令介面。

2.  執行下列 Cmdlet：
    
        Get-CsSite
    
    其會傳回建立集區所在之 siteName 的 siteID。 如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的 [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 。

3.  執行下列 Cmdlet：
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的 [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 。
    
    Exchange Server FQDN 應設定為 Exchange OWA 憑證主體名稱 (SN)，或主體別名 (SAN)。
    
    在 Exchange OWA 中，確認集區的 FQDN 也是可信任的。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的 CAS 伺服器 <EM>不</EM> 是在執行 Exchange 2013 整合通訊 (UM) 的同一部伺服器上組合，請略過此程式中的其餘步驟，並執行本主題稍後的「為 EXCHANGE 2013 CAS 伺服器建立信任的應用程式」過程。 如果您的 CAS 伺服器組合位於執行 Exchange 2013 整合通訊 (UM) 的相同伺服器上，請完成此程式中的步驟，並不要執行本主題稍後的「為 Exchange 2013 CAS 伺服器建立信任的應用程式」過程。

    
    </div>

4.  執行 **[Enable-CsTopology]**。

5.  開啟 Topology Builder，然後下載現有的拓樸。

6.  在左邊的窗格中，展開樹狀目錄，直到找到 **[信任的應用程式伺服器]**。

7.  展開 **[信任的應用程式伺服器]** 節點。

8.  您現在應該會看到列出為信任的應用程式伺服器的 Exchange 2013 CAS 伺服器。

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>若要為 Exchange 2013 CAS 伺服器建立信任的應用程式

1.  啟動 Lync Server 2013 管理命令介面。

2.  如果您的 CAS 伺服器 *沒有* 組合在執行 Exchange 2013 整合通訊 (UM) 的同一部伺服器上，請執行下列 Cmdlet：
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的主題 [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 。

3.  執行 **[Enable-CsTopology]**。

4.  從拓撲產生器，在左邊的窗格中，展開樹狀目錄，直到找到 **[信任的應用程式伺服器]**。

5.  展開 **[信任的應用程式伺服器]** 節點。

6.  您現在應該會看到列出為信任的應用程式伺服器的 Exchange 2013 CAS 伺服器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

