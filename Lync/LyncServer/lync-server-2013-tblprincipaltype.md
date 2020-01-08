---
title: Lync Server 2013：tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblPrincipalType 包含主要類型來分類 tblPrincipal 資料表中的內容。

### <a name="columns"></a>分欄

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ptypeID</p></td>
<td><p>Smallint，not null</p></td>
<td><p>主體類型 ID。</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>Nvarchar （256），not null</p></td>
<td><p>類型的描述。</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit、not null</p></td>
<td><p>如果該類型對應到用於內部用途的主體，則為 True。</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit、not null</p></td>
<td><p>如果該類型是使用者類型，則為 True。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>機碼

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ptypeID</p></td>
<td><p>主鍵。</p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a>主要值

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>標識號</th>
<th>角色</th>
<th>描述</th>
<th>使用者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>每</p></td>
<td><p>沒有已知類型的一般原則。 在 tblPrincipal 表格中未使用。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>pplx-2</p></td>
<td><p>AnyUser</p></td>
<td><p>使用者類型的一般主體。 在 tblPrincipal 表格中未使用。</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>含有群組語義的一般主體。 在 tblPrincipal 表格中未使用。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>SystemUser</p></td>
<td><p>永久聊天伺服器在內部使用的主要原則。</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>500</p></td>
<td><p>使用者</p></td>
<td><p>一般使用者。</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>型</p></td>
<td><p>DC</p></td>
<td><p>Active Directory 網域服務網網域控制站。</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>群組</p></td>
<td><p>Active Directory 安全性群組。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>第</p></td>
<td><p>資料夾</p></td>
<td><p>Active Directory 容器或組織單位。</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的 tblPrincipal](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

