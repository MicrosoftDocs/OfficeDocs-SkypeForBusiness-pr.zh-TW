---
title: Lync Server 2013：執行最佳做法分析程式的需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for running Best Practices Analyzer
ms:assetid: 3c7dc44e-5f8a-40a7-9ebb-9ad707ac0007
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591345(v=OCS.15)
ms:contentKeyID: 48183880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f097da7dc35c63cb385abd7ea233ec85df386a6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511840"
---
# <a name="requirements-for-running-best-practices-analyzer-in-lync-server-2013"></a>在 Lync Server 2013 中執行最佳做法分析程式的需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-19_

您可以使用 Lync Server 2013，最佳做法分析程式來掃描您的 Lync Server 2013 環境。 無法使用它來掃描舊版的環境，而必須使用舊版工具來掃描那些環境。 如需下載和使用 Lync Server 2010 和 Office 通訊伺服器 2007 R2 的最佳做法分析程式的詳細資訊，請參閱《 Lync Server 2010，最佳作法分析器」 [https://go.microsoft.com/fwlink/p/?linkId=210536](https://go.microsoft.com/fwlink/p/?linkid=256358) 和「Office 通訊伺服器2007和 Office 通訊2007伺服器的最佳作法分析程式」 [https://go.microsoft.com/fwlink/p/?linkId=256358](https://go.microsoft.com/fwlink/p/?linkid=210651) 。

在開始您的掃描之前，您應該確定 Lync Server 2013 環境中的所有元件都在執行中和線上。

<div>


> [!NOTE]  
> 取決於 Edge Server 的組態及任何的相關周邊網路設定 (包括防火牆設定及權限)，最佳做法分析程式有可能無法存取並掃描 Edge Server。如果將 Edge Server 涵蓋在掃描中，而報告指出存取 Edge Server 發生問題，最好將 Edge Server 從掃描選項中移除，然後再次執行掃描，報告就不會顯示這個問題。



</div>

</div>

<span> </span>

</div>

</div>

</div>

