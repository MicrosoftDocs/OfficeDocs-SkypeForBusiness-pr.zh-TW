---
title: Lync Server 2013：設定撥出電話的語音路由
description: Lync Server 2013：設定撥出電話的語音路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd0d712295ecdd0e9a517330abcff36021e996d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542209"
---
# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>在 Lync Server 2013 中設定撥出電話的語音路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

Lync Server 2013 語音路由會將目的地電話號碼與一或多個公用交換電話網路 (PSTN) 閘道或 SIP 主幹及一個或多個 PSTN 使用方式記錄產生關聯。

**使用 Lync Server 控制台來查看語音路由**

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  按一下 **[語音路由]**。

3.  按一下 **[路由]**。

4.  從語音路由清單中按兩下語音路由，即可檢視其他屬性，或選取路由，按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。
    
    <div>
    

    > [!NOTE]  
    > 每次僅可檢視單一路由的詳細資訊。

    
    </div>

**使用 Windows PowerShell 查看語音路由**

  - 啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。 您可以使用 Windows PowerShell 和 **Get-CsVoiceRoute** Cmdlet 來查看語音路由。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。
    
    若要查看所有語音路由的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
        Get-CsVoiceRoute
    
    如此將傳回類似如下的資訊：
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> 如需詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-voice-routes.md">Lync Server 2013 中的語音路由</A> 。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)

  - [在 Lync Server 2013 中修改語音路由](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中管理語音路由](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

