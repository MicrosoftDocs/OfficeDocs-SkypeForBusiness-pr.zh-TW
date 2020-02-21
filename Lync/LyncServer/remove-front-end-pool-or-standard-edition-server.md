---
title: 移除前端集區或 Standard Edition server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47aa2edebe202f6ed21d1b802d899faea563feba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>移除前端集區或 Standard Edition server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

本主題會引導您完成移除前端集區或 Standard Edition 前端伺服器的程序。 當您移除前端集區時，即會移除每個前端伺服器集區移除程序的一部分所屬之集區。 當您移除 Standard Edition 前端伺服器時，您必須移除的 SQL 存放區定義拓撲產生器]。

<div>

## <a name="to-remove-a-front-end-server-pool"></a>移除前端伺服器集區

1.  開啟拓撲產生器]。

2.  瀏覽至 [Lync Server 2010] 節點。

3.  展開 [ **Enterprise Edition 前端集區**，依序展開 [前端集區，以滑鼠右鍵按一下您要移除的前端集區，然後按一下**刪除**。

4.  發行拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署精靈。

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>移除 Standard Edition 前端伺服器

1.  開啟拓撲產生器]。

2.  瀏覽至 [Lync Server 2010] 節點。

3.  依序展開 [ **Standard Edition 前端伺服器**，以滑鼠右鍵按一下您要移除以前端伺服器，然後按一下 [**刪除**。

4.  依序展開 [ **SQL 儲存**，以滑鼠右鍵按一下與 Standard Edition 前端伺服器，相關聯的 SQL Server 資料庫，然後按一下 [**刪除**。
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須移除 Standard Edition 前端伺服器組合的 SQL Server 資料庫的定義。

    
    </div>

5.  發行拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署精靈。

</div>

</div>

<span> </span>

</div>

</div>

</div>

