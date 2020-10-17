---
title: Lync Server 2013：將 Lync Server 2013 Standard Edition 部署到現有的 Lync Server 2013 Enterprise
description: Lync Server 2013：將 Lync Server 2013 Standard Edition 部署到現有的 Lync Server 2013 Enterprise。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b233d4e782e716904fca0a2a146b2459e906aa57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571719"
---
# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>將 Lync Server 2013 Standard Edition 部署到現有的 Lync Server 2013 企業版

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

將 Standard Edition server 部署至現有的 Enterprise Edition 部署，類似于部署其他伺服器角色。 Standard Edition server 可能會部署至另一個網站，讓該網站中的使用者能夠駐留在 Standard Edition server，而不是跨廣域網路) 的前端集區 (。 在 [ [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ] 檔的其他區段中已定義安裝新網站及該網站中伺服器的程式。

<div id="sectionSection0" class="section">

**若要定義新網站**

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [ **新增中央網站**]。

3.  在 **[識別網站]** 頁面上，提供網站的名稱並選擇性輸入描述。

4.  遵循用於定義網站拓撲其餘部分的程序。 如需詳細資訊，請參閱 [在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。

5.  發行更新後的拓撲。 如需詳細資訊，請參閱 [在 Lync Server 2013 中發行拓撲](lync-server-2013-publish-the-topology.md)。

6.  設定並安裝 Standard Edition server。
    
    <div>
    

    > [!Caution]  
    > 如果您已部署只有 Standard Edition server 的環境，則您必須使用 [ <STRONG>準備第一個 Standard edition Server</STRONG> ] 連結，從 [Lync Server 部署嚮導] 中開始安裝程式，將初始資料庫檔案安裝到新的 Standard edition server。 將 Standard Edition server 安裝至現有的 Lync Server 2013 部署時，<STRONG>請勿</STRONG>遵循此程式。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

