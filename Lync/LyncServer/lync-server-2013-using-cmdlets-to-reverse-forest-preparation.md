---
title: Lync Server 2013：使用 Cmdlet 進行反向樹系準備
description: Lync Server 2013：使用 Cmdlet 進行反向樹系準備。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acac87bdaeb7e730f93401fa62ea2678a713bb8f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580389"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-06-19_

使用 **Disable-CsAdForest** Cmdlet 來反向樹系準備步驟。

<div>


> [!WARNING]  
> 如果您在也部署舊版 Lync Server 的環境中執行 <STRONG>Disable-CsAdForest</STRONG> 指令程式，則舊版本的通用設定也會被刪除。



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>若要使用 Cmdlet 進行反向樹系準備

1.  以樹系根域的 Domain Admins 群組成員身分登入加入網域的電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    例如：
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Force 參數會指定是否強制執行任務。 如果此參數不存在，則即使樹系中的一個網域仍為 Lync Server 2013 做好準備，此命令也不會執行。 如果指定 Force 參數，不論樹系中其他網域的狀態為何，該動作都會繼續。
    
    如果您未指定 GroupDomain 參數，則預設值為本機網域。

</div>

<div>

## <a name="see-also"></a>另請參閱


[對 Lync Server 2013 執行樹系準備](lync-server-2013-running-forest-preparation.md)  


[準備 Lync Server 2013 的樹系](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

