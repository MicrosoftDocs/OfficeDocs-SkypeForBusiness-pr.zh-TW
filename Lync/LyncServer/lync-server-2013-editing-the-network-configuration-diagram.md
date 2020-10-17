---
title: Lync Server 2013：編輯網路設定圖表
description: Lync Server 2013：編輯網路設定圖表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead2b0b47ec0cb0a98c33d7fff0a644f05f92c71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570589"
---
# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>在 Lync Server 2013 中編輯網路設定圖表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在 Lync Server 2013 中，規劃工具中的大部分工作都是針對網狀圖上專案的 IP 位址和完整功能變數名稱定義 (Fqdn) 中的專案所組成。 在此頁面上輸入的資訊會包含在規劃工具中的報告及其他資訊中。

![規劃工具的網狀圖表](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "規劃工具的網狀圖表")

規劃工具會以預設的 IP 位址和 Fqdn 來建立網狀圖表和預設文字。

若要編輯網路圖和輸入值：

1.  選擇要開始處理的網路區段。 例如，按兩下文字 **access1.contoso.com**。 在開啟的對話方塊中，輸入伺服器 access1.contoso.com 的實際 FQDN 和實際的 IP 位址，取代131.107.155.3。

2.  按一下 **[確定]** 儲存項目。

3.  繼續編輯 IP 位址和 FQDN，提供各硬體負載平衡器的虛擬 IP 位址，或集區中各伺服器的網域名稱系統 (DNS) 負載平衡的伺服器項目。

規劃工具的一項實用功能在於可以漸進地指派 IP 位址範圍和伺服器主機名稱，而不需要設計師分別編輯集區中的每部伺服器。例如：

1.  按兩下集區化的前端伺服器。 當對話方塊開啟時，選取 **[您要使用 IP 和 FQDN 作為此叢集中所有同等級伺服器的起點嗎?]**。

2.  例如，第一部伺服器的開始值是 fe0101.contoso.com 和192.168.21.122 的 IP 位址。

3.  在 [**前端伺服器 FQDN**] 中輸入**Fe0.contoso.com** ，在**前端伺服器的 IP 位址**中輸入**192.168.21.131** ，然後按一下 **[確定]**。

4.  自動遞增值功能會將集區中的所有伺服器更新為 fe01 到 fe06，並將所有 IP 位址從192.168.21.131 更新為136。

完成所有編輯之後，請完成下列步驟以儲存拓撲：

若要儲存規劃工具設計，請 **按一下 [** 檔案]，然後按一下 [ **儲存拓撲** ] 或 [ **另存拓撲**]。 如果出現 **[另存規劃工具]** 對話方塊，請在 **[檔案名稱]** 中輸入檔案的名稱，然後按一下 **[儲存]**。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中編輯設計](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

