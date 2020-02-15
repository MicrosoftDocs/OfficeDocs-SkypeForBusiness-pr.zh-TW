---
title: Lync Server 2013： 還原 Enterprise Edition 成員伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0643cf250e00b447bfac8a1b32c2a3038cff139
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>還原 Lync Server 2013 Enterprise Edition 成員伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-18_

如果執行下列其中一個下列伺服器角色失敗的伺服器，請遵循本主題將伺服器還原程序。 如果有多部伺服器個別失敗了，請針對各伺服器遵循程序進行。

  - 前端伺服器

  - 中繼伺服器

  - Director

  - 常設聊天室伺服器

  - Edge Server

<div>


> [!TIP]  
> 我們建議您採取系統映像複本，再開始還原。 在以免還原期間，您可以使用做為回復點，如此圖所示。 您可能要花映像複本之後安裝作業系統和 SQL Server，並還原或重新註冊憑證。



</div>

<div>

## <a name="to-restore-a-member-server"></a>還原成員伺服器

1.  開頭為失敗的伺服器具有相同的完整的網域名稱 (FQDN) 的乾淨或全新伺服器、 安裝作業系統，並再還原或重新註冊憑證。
    
    <div>
    

    > [!NOTE]  
    > 遵循貴組織的伺服器部署程序執行此步驟。

    
    </div>

2.  使用 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入您要還原的伺服器。

3.  瀏覽至 [Lync Server 安裝資料夾或媒體，並啟動 Lync Server 部署精靈位於\\安裝\\amd64\\Setup.exe。

4.  遵循 [部署精靈] 的指示執行下列作業：
    
    1.  執行 [步驟 1: 安裝本機組態存放區]****，以安裝本機設定檔。
    
    2.  執行**步驟 2： 安裝或移除 Lync Server 元件**安裝 Lync Server 伺服器角色。
    
    3.  執行 [步驟 3: 要求、安裝或指派憑證]****，以指派憑證。
    
    4.  執行 [步驟 4: 啟動服務]****，以啟動伺服器上的服務。
    
    如需執行 [部署精靈的詳細資訊，請參閱部署文件，針對您要還原的伺服器角色。

</div>

</div>

<span> </span>

</div>

</div>

</div>

