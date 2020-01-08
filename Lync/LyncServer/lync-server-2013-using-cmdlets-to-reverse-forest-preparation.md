---
title: Lync Server 2013：使用 Cmdlet 進行反向樹系準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd186fc3b2c6171b49cf3fd4c9e78b8e66b4cc71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-06-19_

使用**Disable CsAdForest** Cmdlet 來反向林準備步驟。

<div>


> [!WARNING]  
> 如果您在同時部署舊版 Lync Server 的環境中執行<STRONG>Disable CsAdForest</STRONG> Cmdlet，則會同時刪除舊版的全域設定。



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>使用 Cmdlet 來反向林準備

1.  以網域管理員群組的成員身分登入加入網域的電腦（在林根網域中）。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    例如：
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Force 參數指定是否強制執行任務。 如果此參數不存在，即使林中的一個網域仍為 Lync Server 2013 準備好，該命令也不會執行。 如果指定了 Force 參數，則無論林中其他網域的狀態為何，該動作都會繼續。
    
    如果您沒有指定 GroupDomain 參數，則預設值為本地域。

</div>

<div>

## <a name="see-also"></a>請參閱


[針對 Lync Server 2013 執行樹系準備](lync-server-2013-running-forest-preparation.md)  


[為 Lync Server 2013 準備樹系](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

