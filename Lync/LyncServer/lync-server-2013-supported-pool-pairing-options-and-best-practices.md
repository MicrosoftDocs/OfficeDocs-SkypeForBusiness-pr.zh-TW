---
title: Lync Server 2013 支援的 [池配對] 選項和最佳做法
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
ms.openlocfilehash: 9090fefba4b80f14382b9b43b5e9ced7cb36b2e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>支援 Lync Server 2013 的池配對選項和最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-03-09_

在兩個資料中心之間的距離沒有限制，包括彼此配對的前端池。 我們建議您在同一個世界區域使用兩個資料中心，並在它們之間進行高速連結。 最好的做法是將兩個資料中心分割得足夠，以避免單一災難同時發生。

您可以跨世界區域進行兩個資料中心，但由於資料複製中的延遲，可能會造成較高的資料遺失。

規劃要配對的池時，您必須記住，只有下列配對是受支援的：

  - 企業版池只能與其他企業版池搭配使用。 同樣地，標準版池只能與其他標準版池成對使用。

  - 物理池只能與其他物理池進行配對。 同樣地，虛擬池只能與其他虛擬池成對。

  - 成對組成的池必須執行相同的作業系統。

拓撲產生器和拓撲驗證都不會以不遵循這些建議的方式來禁止配對兩個池。 例如，拓撲建立器可讓您將企業版池與標準版池配對。 不過，不支援這些類型的配對。

成對中的每個池，都應該有能力，以便在發生災難事件時，從兩個池的所有使用者都能提供服務。

如果您要將企業版池配對，您也可以在後端伺服器上執行高可用性，但適用于標準版池，只提供災害復原測量。

</div>

<span> </span>

</div>

</div>

</div>

