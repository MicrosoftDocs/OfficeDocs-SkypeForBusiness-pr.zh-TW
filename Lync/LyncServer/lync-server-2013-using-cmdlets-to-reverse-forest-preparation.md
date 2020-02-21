---
title: Lync Server 2013： 使用 cmdlet 反向樹系準備
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
ms.openlocfilehash: 4d39992255bfe6f93d9f41380b4f6b5fb9af1f5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>使用 cmdlet 反向樹系準備 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-06-19_

使用**Disable-csadforest** cmdlet 反向樹系準備步驟。

<div>


> [!WARNING]  
> 如果您執行<STRONG>Disable-csadforest</STRONG> cmdlet 也有舊版的環境中部署 Lync Server，舊版的全域設定也會一併刪除。



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>若要使用 cmdlet 反向樹系準備

1.  登入已加入網域的樹系根網域中 Domain Admins 群組成員身分的電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  執行：
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    例如：
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Force 參數會指定是否強制執行工作。 如果這個參數不存在，如果針對 Lync Server 2013 仍然準備即使是一個樹系中的網域，將不會執行命令。 如果指定 Force 參數，則巨集指令將繼續不論樹系中其他網域的狀態。
    
    如果您未指定 GroupDomain 參數，預設值為本機網域。

</div>

<div>

## <a name="see-also"></a>另請參閱


[執行 Lync Server 2013 的樹系準備](lync-server-2013-running-forest-preparation.md)  


[準備樹系的 Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

