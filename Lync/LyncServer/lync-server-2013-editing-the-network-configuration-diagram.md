---
title: Lync Server 2013：編輯網路設定圖表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2772cad1d1a16aa0363b1ab50d0bcaadacb91a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>在 Lync Server 2013 中編輯網路設定圖表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在 Lync Server 2013 中，設計工具的大部分工作都是由定義 IP 位址的專案，以及網狀圖表專案的完整功能變數名稱（Fqdn）。 在此頁面上輸入的資訊會納入至 [規劃工具] 中所含的報告及其他資訊。

![規劃工具網狀圖](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "規劃工具網狀圖")

規劃工具會建立含 IP 位址和 Fqdn 預設文字的網狀圖表。

若要編輯 network 圖表及輸入值：

1.  選擇要開始使用的網路區段。 例如，按兩下文字 [ **access1.contoso.com**]。 在開啟的對話方塊中，輸入 [伺服器 access1.contoso.com] 的實際 FQDN，以及實際的 IP 位址（取代131.107.155.3）。

2.  按一下 **[確定]** 儲存專案。

3.  繼續編輯 IP 位址和 Fqdn，提供硬體負載平衡器的虛擬 IP 位址或網域名稱系統（DNS）的伺服器專案在池中的伺服器負載平衡。

規劃工具有一個實用的功能，就是它可以逐漸指派 IP 位址和伺服器主機名稱的範圍，而不需要設計者在池中編輯每個獨立的伺服器。 例如：

1.  按兩下共端的前端伺服器。 對話方塊開啟時，請選取 [**您想要將 IPs 和 FQDN 作為此群集中所有等價伺服器的起始點嗎？**]。

2.  例如，第一個伺服器的起始值是 fe0101.contoso.com，IP 位址是192.168.21.122。

3.  在 [**前端伺服器 FQDN**] 中輸入**Fe0.contoso.com** ，在**前端伺服器 IP 位址**中輸入**192.168.21.131** ，然後按一下 **[確定]**。

4.  [自動遞增值] 功能會將池中的所有伺服器更新為 fe01 到 fe06，並將所有 IP 位址從192.168.21.131 移至136。

完成所有編輯之後，請完成下列步驟以儲存拓朴：

若要儲存規劃工具設計，請**按一下 [** 檔案]，然後按一下 [**儲存拓撲**] 或 [**另存拓撲為**]。 如果出現 [**儲存規劃工具**] 對話方塊，請在 [**檔案名**] 中輸入檔案名，然後按一下 [**儲存**]。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中編輯設計](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

