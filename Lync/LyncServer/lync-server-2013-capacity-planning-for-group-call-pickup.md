---
title: Lync Server 2013：群組呼叫裝貨的容量規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d694b20d026d83b4cef37c713e38ab8066e22f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 中的群組通話裝貨產能規劃

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-12_

<div id="sectionSection0" class="section">

下表說明您可以用來做為容量規劃需求基礎的 [群組呼叫挑選使用者模型]。

<div>


> [!IMPORTANT]  
> [群組呼叫挑選] 是以 [通話駐留] 應用程式為基礎。 請記住，對於災難復原容量規劃，配對池的每個池都應該能夠處理通話駐留服務的工作負荷，包括兩個池中的群組呼叫。



</div>

### <a name="group-call-pickup-user-model"></a>群組呼叫使用者模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>衡量</th>
<th>每個前臺端池（含8個前端伺服器）</th>
<th>每個標準版 server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>建議的每個群組使用者數</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>建議的群組數</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>針對群組呼叫挑選啟用的每個池的使用者數目上限</p></td>
<td><p>25000</p></td>
<td><p>3,000</p></td>
</tr>
<tr class="even">
<td><p>每分鐘針對每個群組呼叫啟用群組通話的最大來電率</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>每分鐘由每個群組呼叫每個群組的使用者所檢索來電的最大比率</p></td>
<td><p>200</p></td>
<td><p>位</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>對於不超過八個前端伺服器的前端池，請線性地計算度量單位。 例如，如果您的前端池有一個前端伺服器，請將最大負載計算為表格中顯示的值1/8。</P>
> <LI>
> <P>只要您不超過每個池中的使用者數目上限，您就可以增加或減少每個群組的使用者數和群組數。 例如，您的標準版伺服器可以有120個群組，每個群組含25個使用者，因為為群組通話挑選啟用的使用者數目仍在使用者模型最大值（也就是，120群組乘以25個3000使用者為群組通話挑選的使用者）。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

