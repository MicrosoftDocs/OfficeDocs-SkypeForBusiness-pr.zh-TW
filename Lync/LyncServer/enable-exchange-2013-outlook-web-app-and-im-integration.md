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
ms.openlocfilehash: 0bd9fb94dd0f068547819aa884b608ac6ddf7e39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>啟用 Exchange 2013 Outlook Web App 與 IM 整合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

若要啟用 Exchange 2013 Outlook Web Access （OWA）與立即訊息（IM）與 Lync Server 2013 整合，您必須將 Exchange 2013 用戶端存取伺服器（CAS）伺服器新增到 Lync Server 2013 拓撲，成為受信任的應用程式伺服器。

<div>

## <a name="to-create-a-trusted-application-pool"></a>建立信任的應用程式池

1.  啟動 Lync Server 2013 管理命令介面。

2.  執行下列 Cmdlet：
    
        Get-CsSite
    
    這會傳回您在其中建立池的 siteName 的 siteID。 如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的[CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 。

3.  執行下列 Cmdlet：
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的[新 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 。
    
    Exchange 伺服器 FQDN 應該設定為 Exchange OWA 證書受領人名稱（SN.EXE），或 Subject 替代名稱（SAN）。
    
    在 [Exchange OWA] 中，確認該池的 FQDN 也是受信任的。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的 CAS 伺服器<EM>無法</EM>在執行 Exchange 2013 整合通訊（UM）的同一台伺服器上 collocated，請跳過此程式中的其餘步驟，然後執行本主題稍後的「建立 EXCHANGE 2013 CAS 伺服器的信任的應用程式」程式。 如果您的 CAS 伺服器是在執行 Exchange 2013 整合通訊（UM）的同一台伺服器上 collocated，請完成此程式中的步驟，並不要執行本主題稍後的「為 Exchange 2013 CAS 伺服器建立信任的應用程式」程式。

    
    </div>

4.  執行 [ **Enable-CsTopology**]。

5.  開啟拓撲建立器並下載現有的拓撲。

6.  在左窗格中，展開樹狀結構，直到您到達**受信任的應用程式伺服器**為止。

7.  展開 [**受信任的應用程式伺服器**] 節點。

8.  您現在應該會看到 [Exchange 2013 CAS 伺服器] 列為受信任的應用程式伺服器。

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>若要為 Exchange 2013 CAS 伺服器建立信任的應用程式

1.  啟動 Lync Server 2013 管理命令介面。

2.  如果您的 CAS 伺服器*無法*在執行 Exchange 2013 整合通訊（UM）的同一台伺服器上 collocated，請執行下列 Cmdlet：
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的 [[新-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) ] 主題。

3.  執行 [ **Enable-CsTopology**]。

4.  從 [拓撲建立器] 的左窗格中，展開樹狀結構，直到您到達**受信任的應用程式伺服器**為止。

5.  展開 [**受信任的應用程式伺服器**] 節點。

6.  您現在應該會看到 [Exchange 2013 CAS 伺服器] 列為受信任的應用程式伺服器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

