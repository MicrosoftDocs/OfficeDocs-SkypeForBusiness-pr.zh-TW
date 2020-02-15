---
title: 'Lync Server 2013: Microsoft Lync 用戶端設定連接埠範圍'
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
ms.openlocfilehash: ea0300b042dc124f0fb8bf523221e39128cbf57a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>針對您在 Lync Server 2013 中的 Microsoft Lync 用戶端設定連接埠範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-04-22_

根據預設，Lync 用戶端應用程式可以使用任何連接埠之間連接埠 1024年與 65535 時參與通訊工作階段;這是因為特定的連接埠範圍不會自動啟用用戶端。 然而為了使用服務品質，您必須將各種流量類型重新分派 (音訊、視訊、媒體、應用程式共用及檔案傳輸) 至一系列的唯一連接埠範圍。 使用 Set-CsConferencingConfiguration Cmdlet 可達成此目的。

<div>


> [!NOTE]  
> 使用者無法進行這些變更本身。 連接埠變更只能由系統管理員使用 Set-csconferencingconfiguration 指令程式。



</div>

您可以決定哪一個連接埠範圍可以目前用來進行通訊工作階段執行從 Microsoft Lync Server 2013 管理命令介面中的下列命令：

    Get-CsConferencingConfiguration

假設不您已對會議設定進行任何變更，因為您已安裝 Lync Server 2013，您應該會得到資訊，包含這些屬性值：

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

若您仔細看前面的輸出，就會注意到兩項重點。 首先，ClientMediaPortRangeEnabled 屬性是設為 False：

    ClientMediaPortRangeEnabled : False

這是重要的因為此屬性設為 False，Lync 用戶端會使用任何可用的連接埠連接埠 1024年之間和 65535 時參與通訊工作階段中。這是不論任何其他連接埠設定 （例如，ClientMediaPort 或 ClientVideoPort），則為 true。 若您想要限制特定一組連接埠的流量 (您如果打算實作服務品質時，就會需要這麼做)，就必須先啟用用戶端媒體連接埠範圍。 可以完成，使用下列 Windows PowerShell 命令：

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

前面的命令會啟用全域會議組態設定集合的用戶端媒體連接埠；不過這些設定也可套用至網站範圍及/或服務範圍 (僅限會議伺服器服務)。若要啟用特定網站或伺服器的用戶端媒體連接埠範圍，請在呼叫 Set-CsConferencingConfiguration 時指定該網站或伺服器的識別：

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

或者，您也可使用此命令，同時啟用所有會議組態設定的連接埠範圍：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

您注意到的第二項重點是範例輸出顯示，根據預設，針對每個網路流量類型所設定的媒體連接埠範圍皆為相同：

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

為了實作 QoS，其中的每個連接埠範圍皆必須是唯一的連接埠範圍。例如，您可能設定了如下的連接埠範圍：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端流量類型</th>
<th>連接埠開始</th>
<th>連接埠範圍</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>影片</p></td>
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


在前面的表格中，用戶端連接埠範圍即為針對您伺服器所設定之連接埠範圍的子網路。例如，在伺服器上將應用程式共用設定為使用連接埠 40803 到 49151；在用戶端電腦上將應用程式共用設定為使用連接埠 42000 到 42019。這麼做也是為了使 QoS 的管理較為容易：其實用戶端連接埠不需要是伺服器使用之連接埠的子網路 (例如，您可在用戶端電腦上將應用程式共用設定為使用連接埠 10000 到 10019)。但仍建議您將用戶端連接埠範圍設為伺服器連接埠範圍的子網路。

此外，您可能還有注意到，在伺服器上針對應用程式共用獨立設定了 8348 個連接埠，但用戶端上的應用程式共用僅獨立設定了 20 個連接埠。雖然這也是推薦的設定，卻不是需要嚴格遵守的規則。一般而言，您可將每個可用的連接埠視為代表單一通訊工作階段：若您在連接埠範圍中有 100 個可用的連接埠，表示先前提到的電腦最多可隨時參與 100 個通訊工作階段。因為伺服器可能會比用戶端參與更多的交談，所以在伺服器上開啟比用戶端更多的連接埠也很合理。為應用程式共用在用戶端上獨立設定 20 個連接埠，表示使用者可在特定裝置上同時參與 20 個應用程式共用工作階段。這對於您絕大多數的使用者而言應該已足夠使用。

若要將先前的連接埠範圍指派給您的全域集合的會議組態設定中，您可以使用下列的 Lync Server 管理命令介面命令：

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

或是使用此命令將這些相同的連接埠範圍指派給所有會議組態設定：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

個別使用者必須從 Lync 登出，然後再重新登入才會實際這些變更生效。

<div>


> [!NOTE]  
> 您可以也可以讓用戶端的媒體連接埠範圍，並接著指派這些連接埠範圍，使用單一命令。 例如：<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

