---
title: Lync Server 2013： 匯出語音路由測試案例
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
ms.openlocfilehash: d871379f9c9be161aec879b7ca8da16ac40e2b5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>匯出語音路由測試案例在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

測試案例提供方法讓您在組織中測試語音路由： 您定義要撥打號碼等事項以及要採用的撥號對應表計劃和語音原則和 Lync Server 就可以確認，在這些條件，提供的號碼可以順利進行路由傳送至 PSTN 網路。

測試案例，可以建立使用 Lync Server Control Panel，通常會儲存只能在其中最初建立及執行這種情況的伺服器上。 不過，這些測試案例可以用 XML 檔案 (副檔名為 .vtest) 的形式匯出，然後匯入到其他伺服器上。 如此可讓您在位於拓樸中不同點的不同電腦上執行相同的測試。

<div>

## <a name="to-export-a-voice-routing-test-case"></a>若要匯出語音路由測試案例

1.  在 Lync Server 控制台中，按一下 [**語音路由**，然後按一下 [**測試語音路由**。

2.  在 **[測試語音路由]** 索引標籤上，選取要匯出的測試案例。如果要選取多個測試案例，請按一下要匯出的第一個案例，然後按住 Ctrl 鍵，再選取其他要匯出的案例。

3.  依序按一下 **[動作]** 和 **[匯出測試案例]**。

4.  在 **[另存新檔]** 對話方塊中，選取要儲存匯出的測試案例的資料夾，然後在 **[檔案名稱]** 方塊中輸入產生的 XML 檔案的名稱。請注意，如果您匯出多個測試案例，這些測試案例會全部儲存為單一 XML 檔案。

5.  若要儲存測試案例，按一下 **[儲存]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[匯入 Lync Server 2013 中的語音路由測試案例](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

