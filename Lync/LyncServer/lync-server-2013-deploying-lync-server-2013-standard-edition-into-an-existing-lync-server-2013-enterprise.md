---
title: Lync Server 2013：將 Lync Server 2013 Standard Edition 部署到現有 Lync Server 2013 Enterprise 中
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c505a692590662adf03e48d695b3c1ff089d8d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>將 Lync Server 2013 Standard Edition 部署到現有 Lync Server 2013 Enterprise 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

將標準版伺服器部署至現有的企業版部署，與部署其他伺服器角色類似。 標準版伺服器可能會部署至另一個網站，允許該網站的使用者駐留在標準版伺服器上，而不是在廣域網路（WAN）中的前端池。 在該網站中安裝新網站和伺服器的程式，已在 [[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ] 檔的其他章節中定義。

<div id="sectionSection0" class="section">

**定義新網站**

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [**新的中央網站**]。

3.  在 [**識別網站**] 頁面上，提供網站的名稱，並選擇性地輸入描述。

4.  遵循定義網站拓撲其餘部分的程式。 如需詳細資訊，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。

5.  發佈更新後的拓撲。 如需詳細資訊，請參閱[在 Lync Server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)。

6.  設定和安裝標準版伺服器。
    
    <div>
    

    > [!Caution]  
    > 如果您已部署只有標準版 server 的環境，您就會從 Lync Server 部署嚮導開始進行設定程式，方法是使用 [<STRONG>準備第一個標準版 Server</STRONG> ] 連結，將初始資料庫檔案安裝到新的標準版伺服器。 將標準版伺服器安裝至現有的 Lync Server 2013 部署時，<STRONG>請勿</STRONG>遵循該程式。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

