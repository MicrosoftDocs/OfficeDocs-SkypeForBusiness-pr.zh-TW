---
title: Lync Server 2013：匯出語音路由測試案例
description: Lync Server 2013：匯出語音路由測試案例。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934bd183a17c46cf82fe5bc04faaa55a9bbe4731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564779"
---
# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>在 Lync Server 2013 中匯出語音路由測試案例

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

測試案例提供一種方法，讓您在組織中測試語音路由：您可以定義要撥打的號碼，以及要採用的撥號對應表和語音原則等事項，然後 Lync Server 才能確認所提供的號碼可成功路由傳送至 PSTN 網路。

您可以使用 Lync Server 控制台建立的測試案例通常只會儲存在先前建立及執行案例的伺服器上。 不過，這些測試案例可以用 XML 檔案 (副檔名為 .vtest) 的形式匯出，然後匯入到其他伺服器上。 如此可讓您在位於拓樸中不同點的不同電腦上執行相同的測試。

<div>

## <a name="to-export-a-voice-routing-test-case"></a>若要匯出語音路由測試案例

1.  在 [Lync Server 控制台] 中，按一下 [ **語音路由** ]，然後按一下 [ **測試語音路由**]。

2.  在 **[測試語音路由]** 索引標籤上，選取要匯出的測試案例。如果要選取多個測試案例，請按一下要匯出的第一個案例，然後按住 Ctrl 鍵，再選取其他要匯出的案例。

3.  依序按一下 **[動作]** 和 **[匯出測試案例]**。

4.  在 **[另存新檔]** 對話方塊中，選取要儲存匯出的測試案例的資料夾，然後在 **[檔案名稱]** 方塊中輸入產生的 XML 檔案的名稱。請注意，如果您匯出多個測試案例，這些測試案例會全部儲存為單一 XML 檔案。

5.  若要儲存測試案例，按一下 **[儲存]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中匯入語音路由測試案例](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

