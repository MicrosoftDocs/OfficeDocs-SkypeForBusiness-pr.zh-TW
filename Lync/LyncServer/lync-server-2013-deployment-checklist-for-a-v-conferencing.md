---
title: Lync Server 2013 部署檢查清單，a / V 會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0c48d78c33c652f7a28e277600fa957cb6fd1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a>部署檢查清單 a / V 會議在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-30_

在部署其他 Lync Server 2013 元件，部署 A / V 會議會要求您使用拓撲產生器來建立及發行納入會議的拓撲。

<div>

## <a name="deployment-sequence"></a>部署順序

您可以將會議部署在您部署初始拓撲的同時或之後您已部署至少一個前端集區或 Standard Edition server。

</div>

<div>

## <a name="conferencing-deployment-process"></a>會議部署程序

下表提供將會議部署至現有拓撲所需的步驟概觀。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>階段</th>
<th>步驟</th>
<th>角色和群組成員資格</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安裝必備硬體和軟體</strong></p></td>
<td><p>前端伺服器的前端集區及 Standard Edition server 上執行會議。 安裝這些伺服器除必條件外，沒有額外的硬體或軟體需求。</p>
<div>

> [!NOTE]  
> Lync Server 2013 使用 Office Web Apps 與 Office Web Apps Server 來處理共用和 PowerPoint 簡報的轉譯。 如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">設定整合 Office Web Apps Server 與 Lync Server 2013</A>。


</div></td>
<td><p>為本機系統管理員成員之網域使用者</p></td>
<td><p>支援文件中<a href="lync-server-2013-supported-hardware.md">的 Lync Server 2013 支援硬體</a></p>
<p>支援文件中的 [ <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的伺服器軟體和基礎結構支援</a></p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">決定您的系統需求，針對 Lync Server 2013</a>中規劃文件。</p>
<p>規劃文件中<a href="lync-server-2013-technical-requirements-for-archiving.md">的 technical requirements for Lync Server 2013 中的封存</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>建立適當的內部拓撲以支援會議</strong></p></td>
<td><p>執行拓撲產生器來將會議新增至拓撲，並再發行拓撲。</p></td>
<td><p>定義拓撲，須以本機使用者群組成員帳戶進行</p>
<p>若要發行拓撲，這是 Domain Admins 群組和 RTCUniversalServerAdmins 群組的成員，且用於 Lync Server 2013 檔案存放區 （以便拓撲產生器可以設定必要的 Dacl） 的檔案共用具有完整控制權限 （讀取/寫入/修改） 的帳戶</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">定義和設定拓撲在拓撲產生器中的 Lync Server 2013</a>部署文件中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>設定會議原則及支援</strong></p></td>
<td><p>使用 Lync Server 2013 控制台] 或 [Lync Server 管理命令介面來設定會議設定。</p></td>
<td><p>以 RTCUniversalServerAdmins 群組 (僅限 Windows PowerShell)，或將使用者指派給] 或 CSAdministrator 角色</p></td>
<td><p>作業文件中的<a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的 conferencing policies</a> 。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的會議概觀](lync-server-2013-overview-of-conferencing.md)  
[Lync Server 2013 中定義會議需求](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

