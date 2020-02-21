---
title: Lync Server 2013： 容量規劃群組來電接聽
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
ms.openlocfilehash: d0fa12b04507e5b42767d551af4b4b9c004175b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>容量規劃的 Lync Server 2013 中的 [群組來電接聽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-12_

<div id="sectionSection0" class="section">

下表說明您可以使用容量規劃需求為基礎的群組來電接聽使用者模型。

<div>


> [!IMPORTANT]  
> 群組來電接聽為基礎的通話駐留應用程式。 請記住，災害復原容量規劃，配對集區的每個集區應該能夠處理通話駐留服務，包括群組來電接聽，在兩個集區中的工作負載。



</div>

### <a name="group-call-pickup-user-model"></a>群組通話收取] 目錄的使用者模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>評量</th>
<th>每個前端集區 （使用 8 前端伺服器）</th>
<th>每個 Standard Edition 伺服器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>建議的每個群組的使用者數目</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>建議的群組數目</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>每個啟用群組來電接聽的集區的使用者數目上限</p></td>
<td><p>25,000</p></td>
<td><p>3000</p></td>
</tr>
<tr class="even">
<td><p>來電至群組來電接聽啟用每個每分鐘的集區的使用者總數的最大速率</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>擷取的每個每分鐘的集區的使用者與群組來電接聽通話的最大速率</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>針對擁有少於八個前端伺服器的前端集區，請以線性方式計算度量。 例如，如果您的前端集區有一部前端伺服器，計算的最高負載為 1/8 表格中所顯示的值。</P>
> <LI>
> <P>您可以增加或減少建議的每個群組的使用者數目和群組的數目，只要您不能超過的每個集區的使用者數目上限。 例如，Standard Edition server 可以有 120 群組有 25 位使用者每個群組，因為仍在使用者模型最大值 （亦即 120 群組次數 25 位使用者為已啟用群組來電接聽 3000 使用者） 是已啟用群組來電接聽的使用者數目。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

