---
title: Lync Server 2013：還原企業版成員伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83f0283dc6525dbb75ce74809bd88f4e962a9aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>在 Lync Server 2013 中還原企業版成員伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

如果執行下列其中一個伺服器角色的伺服器失敗，請遵循本主題中的程式來還原伺服器。 如果多個伺服器獨立失敗，請依照每個伺服器的程式執行。

  - 前端伺服器

  - 中繼伺服器

  - Director

  - 常設聊天室伺服器

  - Edge 伺服器

<div>


> [!TIP]  
> 我們建議您先取得系統的影像複本，然後再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生的問題。 您可能會想要在安裝作業系統與 SQL Server 之後拍攝影像複本，並還原或重新註冊憑證。



</div>

<div>

## <a name="to-restore-a-member-server"></a>若要還原成員伺服器

1.  從有與失敗伺服器相同的完整功能變數名稱（FQDN）開始，清除或新伺服器，安裝作業系統，然後還原或重新註冊證書。
    
    <div>
    

    > [!NOTE]  
    > 遵循貴組織的伺服器部署程式來執行此步驟。

    
    </div>

2.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入您要還原的伺服器。

3.  流覽至 Lync Server 安裝資料夾或媒體，然後啟動位於\\安裝程式\\Amd64\\setup.exe 的 lync server 部署嚮導。

4.  遵循 [部署嚮導] 執行下列動作：
    
    1.  執行**步驟1：安裝本機配置存放區**以安裝本機配置檔案。
    
    2.  執行**步驟2：設定或移除 Lync Server 元件**以安裝 lync server server 角色。
    
    3.  執行**步驟3：要求、安裝或指派憑證**來指派憑證。
    
    4.  執行**步驟4：啟動服務**以在伺服器上啟動服務。
    
    如需執行 [部署嚮導] 的詳細資訊，請參閱您要還原之伺服器角色的部署檔。

</div>

</div>

<span> </span>

</div>

</div>

</div>

