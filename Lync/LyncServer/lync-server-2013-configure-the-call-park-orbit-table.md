---
title: Lync Server 2013： 設定通話駐留軌道表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03cb3556ab0111d7bc61de6bc0914b5a3514a7cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Lync Server 2013 中設定通話駐留軌道表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-10_

通話駐留使用軌道駐留通話。 使用者可以駐留與擷取通話之前，您必須設定通話駐留軌道表。 您需要指定範圍的分機號碼 （軌道） 組織會保留駐留通話，並定義這些範圍的路由，藉由指定的通話駐留集區處理每個範圍。 當您定義軌道範圍時，目標是具有足夠的軌道，因此任何一個軌道不會重複使用過快，但不是太軌道您限制適用於使用者的分機或其他服務的數目。 您可以建立多個通話駐留軌道範圍，每個 Lync 伺服器集區部署通話駐留應用程式的位置。 每個通話駐留軌道範圍必須擁有的全域唯一的名稱以及一組獨特的副檔名。

<div>


> [!IMPORTANT]  
> 軌道範圍通常圍繞 100 或更少的軌道。 前提是它小於最大值為 10000 軌道範圍每以及每個集區有 50000 個以下的軌道，每個範圍可以是更大。 如果範圍是太小，軌道更快速地重複使用。



</div>

針對軌道範圍使用虛擬分機 （沒有任何使用者或電話指派給他們的分機） 區塊。

<div>


> [!NOTE]  
> 不支援將直接向內撥號 (DID) 號碼指派為中通話駐留軌道數字軌道表。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

[建立或修改通話駐留軌道範圍在 Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

