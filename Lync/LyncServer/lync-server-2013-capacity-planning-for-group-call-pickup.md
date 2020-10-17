---
title: Lync Server 2013：群組呼叫收取的容量規劃
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
ms.openlocfilehash: c073ea360e00b196e6cf30b6bb6f204d37532ae0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512810"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 中群組呼叫收取的容量規劃

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-12_

<div id="sectionSection0" class="section">

下表說明您可以用來作為容量規劃需求基礎的群組呼叫收取使用者模型。

<div>


> [!IMPORTANT]  
> 群組呼叫收取是以通話駐留應用程式為基礎。 請記住，針對嚴重損壞修復容量規劃，成對集區的每個集區都應該可以處理通話駐留服務的工作負載，包括兩個集區中的群組呼叫收取。



</div>

### <a name="group-call-pickup-user-model"></a>群組呼叫收取使用者模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>計量</th>
<th>每個前端伺服器集區 (8 部前端伺服器) </th>
<th>每個 Standard Edition server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>每個群組的使用者建議數量</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>建議的群組數目</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>群組呼叫收取啟用每個集區的使用者數目上限</p></td>
<td><p>25,000</p></td>
<td><p>3000</p></td>
</tr>
<tr class="even">
<td><p>每分鐘針對每個集區啟用群組來電收取的總來電數上限</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>每分鐘由使用者每個集區呼叫一次，每個集區的呼叫率上限</p></td>
<td><p>200</p></td>
<td><p>0.25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>前端伺服器的前端集區少於8部，以線性方式計算度量。 例如，如果您的前端集區有一部前端伺服器，請將表格中所顯示的值的最大負載計算為1/8。</P>
> <LI>
> <P>您可以增加或減少每個群組的使用者人數和群組數目，只要您不要超過每個集區的最大使用者數目。 例如，您的 Standard Edition server 可以每個群組有25位使用者的120群組，因為為群組呼叫收取的使用者人數仍然在使用者模型中的最大 (，也就是120群組乘以25位3000使用者為使用者啟用群組呼叫收取) 的使用者。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

