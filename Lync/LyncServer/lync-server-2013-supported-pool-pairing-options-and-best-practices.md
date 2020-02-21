---
title: Lync Server 2013 支援的集區配對選項及最佳作法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d33bc5e9622728fb4ee9c2a6a566e6010466d577
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>支援的集區配對選項和 Lync Server 2013 的最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017年-03-09_

將要包含與彼此配對之前端集區的兩個資料中心之間，並沒有距離的限制。建議您在相同的地區設定中使用兩個資料中心，彼此以高速連結。兩個資料中心最好分隔得夠遠，以避免單一災害同時衝擊到兩個資料中心。

擁有跨地理區域的兩個資料中心是可行的，但是可能會因為資料複寫延遲，而導致資料遺失的風險較高。

當您規劃哪些集區配對時，您必須記住，只有下列配對受支援：

  - Enterprise Edition 集區只能與其他 Enterprise Edition 集區配對。同樣地，Standard Edition 集區只能與其他 Standard Edition 集區配對。

  - 實體集區只能與其他實體集區配對。同樣地，虛擬集區只能與其他虛擬集區配對。

  - 一起配對的集區必須執行相同的作業系統。

拓撲產生器或拓撲驗證都不會禁止以非建議的方式來將兩個集區配對。 例如，拓撲產生器可讓您將 Enterprise Edition 集區與 Standard Edition 集區配對。 不過，不支援這些類型的配對。

配對中的每個集區都有在發生災害時，從這兩個集區服務所有使用者的能力。

如果您將 Enterprise Edition 集區配對，也可以在後端伺服器上實作高可用性，但若是 Standard Edition 集區配對，就只有災害復原措施可用。

</div>

<span> </span>

</div>

</div>

</div>

