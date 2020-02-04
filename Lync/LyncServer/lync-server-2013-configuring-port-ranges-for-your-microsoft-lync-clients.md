---
title: Lync Server 2013：為您的 Microsoft Lync 用戶端配置埠範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6405ff6738315476efb7ee65f6d5e020a7cf28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>在 Lync Server 2013 中為您的 Microsoft Lync 用戶端設定埠範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-22_

根據預設，Lync 用戶端應用程式在通訊會話中參與時，可以使用埠1024和65535之間的任何埠;這是因為不會針對用戶端自動啟用特定的埠範圍。 不過，若要使用服務品質，您需要將各種類型的流量（音訊、影片、媒體、應用程式共用及檔案傳輸）重新指派到一系列的唯一端口範圍。 您可以使用 CsConferencingConfiguration Cmdlet 來完成這項工作。

<div>


> [!NOTE]  
> 最終使用者無法自行進行這些變更。 只有系統管理員才能使用 CsConferencingConfiguration Cmdlet 進行埠變更。



</div>

您可以從 Microsoft Lync Server 2013 管理命令介面中執行下列命令，以判斷通訊會話目前使用的是哪個埠範圍：

    Get-CsConferencingConfiguration

假設您在安裝 Lync Server 2013 後沒有進行任何對會議設定所做的變更，您應該會返回包含這些屬性值的資訊：

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

如果您仔細查看上述輸出，您會看到兩個重要事項。 首先，ClientMediaPortRangeEnabled 屬性會設定為 False：

    ClientMediaPortRangeEnabled : False

這個重要的是，因為當這個屬性設定為 False 時，Lync 用戶端會在通訊會話中參與時，使用埠1024和65535之間的任何可用埠;無論任何其他的埠設定（例如，ClientMediaPort 或 ClientVideoPort），都是如此。 如果您想要將使用量限制在指定的一組埠（如果您是在執行服務品質時進行規劃），您必須先啟用用戶端媒體埠範圍。 可以使用下列 Windows PowerShell 命令完成：

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

上述命令可讓用戶端媒體埠範圍用於全域集合會議設定。不過，這些設定也可以套用至網站範圍和/或服務範圍（僅適用于會議服務器服務）。 若要啟用特定網站或伺服器的用戶端媒體埠範圍，請在呼叫 Set-CsConferencingConfiguration 時指定該網站或伺服器的身分識別：

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

或者，您也可以使用此命令同時啟用所有會議設定的埠範圍：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

您會注意到的第二個重要事項是，樣本輸出顯示針對每種類型的網路流量所設定的媒體埠範圍是完全相同的：

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

為了實現 QoS，這些埠範圍中的每一個都必須是唯一的。 例如，您可以設定埠範圍，如下所示：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端流量類型</th>
<th>埠開始</th>
<th>埠範圍</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>顯示器</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>應用程式共用</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>檔案傳輸</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


在前一個表格中，用戶端埠範圍代表伺服器設定的埠範圍的子集。 例如，在伺服器上，應用程式共用已設定為使用埠40803到 49151;在用戶端電腦上，應用程式共用設定為使用埠42000到42019。 如此一來，也主要是為了簡化 QoS 的管理：用戶端埠不需要代表伺服器上所用埠的子集。 （例如，您可以在用戶端電腦上設定要使用的應用程式共用，比如說埠10000到10019。）不過，建議您將用戶端埠範圍設為伺服器埠範圍的子集。

此外，您可能已經注意到8348埠已針對伺服器上的應用程式共用而設定，但用戶端上的應用程式共用只留有20個埠。 我們也建議您這麼做，但不是很難且快速的規則。 一般來說，您可以考慮每個可用的埠代表單一通訊會話：如果埠範圍中有可用的100埠，表示有問題的電腦在任何特定時間都可以參與（最多100通訊會話）。 因為伺服器可能會參與許多用戶端的交談，所以在伺服器上開啟的埠數會比用戶端多。 為用戶端上的應用程式共用設定20個埠，意味著使用者可以同時在指定的裝置上參與20個應用程式共用會話。 這對於絕大多數使用者而言，都應該有足夠的證明。

若要將先前的埠範圍指派給您的全域會議設定設定，您可以使用下列 Lync Server Management Shell 命令：

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

或者，您可以使用這個命令，為所有的會議設定指派相同的埠範圍：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

個別使用者必須從 Lync 登出，然後重新登入，這些變更才會生效。

<div>


> [!NOTE]  
> 您也可以使用單一命令來啟用用戶端媒體埠範圍，然後指派這些埠範圍。 例如：<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

