---
title: Lync Server 2013：還原 Enterprise Edition 成員伺服器
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
ms.openlocfilehash: b958b10fc8c801d680cf17cac8fb493eae82df8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511440"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>在 Lync Server 2013 中還原 Enterprise Edition 成員伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

如果執行下列其中一個伺服器角色的伺服器失敗，請遵循本主題中的程式來還原伺服器。 如果有多部伺服器個別失敗了，請針對各伺服器遵循程序進行。

  - 前端伺服器

  - 中繼伺服器

  - Director

  - 常設聊天室伺服器

  - Edge Server

<div>


> [!TIP]  
> 建議您先取得系統的影像複本，再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生問題。 在您安裝作業系統和 SQL Server 之後，您可能會想要使用影像副本，並還原或重新註冊憑證。



</div>

<div>

## <a name="to-restore-a-member-server"></a>還原成員伺服器

1.  開始使用具有相同完整功能變數名稱 (FQDN) 為失敗伺服器的全新伺服器，然後安裝作業系統，再還原或重新註冊憑證。
    
    <div>
    

    > [!NOTE]  
    > 遵循貴組織的伺服器部署程序執行此步驟。

    
    </div>

2.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入您要還原的伺服器。

3.  流覽至 [Lync Server 安裝] 資料夾或媒體，然後啟動位於 \\ setup amd64Setup.exe 的 Lync Server 部署嚮導 \\ \\ 。

4.  遵循 [部署精靈] 的指示執行下列作業：
    
    1.  執行 [步驟 1: 安裝本機組態存放區]****，以安裝本機設定檔。
    
    2.  執行 **步驟2：安裝或移除 Lync Server 元件** ，以安裝 lync server server role。
    
    3.  執行 [步驟 3: 要求、安裝或指派憑證]****，以指派憑證。
    
    4.  執行 [步驟 4: 啟動服務]****，以啟動伺服器上的服務。
    
    如需執行部署嚮導的詳細資訊，請參閱部署檔中您要還原的伺服器角色。

</div>

</div>

<span> </span>

</div>

</div>

</div>

