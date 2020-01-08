---
title: Lync Server 2013 會議的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 719bd7f8de6fd7356a6b2e454cc86e9aa85abd6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中會議的技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-25_

針對 Lync Server 2013、電話撥入式會議、A/V 會議、立即訊息（IM）會議和網路會議功能，都必須在前端伺服器上執行。

本節詳細說明這些伺服器的硬體和軟體需求，以及支援的 collocation。

電話撥入式會議是包含各種元件的功能。 某些元件是與電話撥入式會議相關的，而有些則是企業語音元件。 本節說明特定于電話撥入式會議的元件需求。 如需有關中繼伺服器與公用交換電話網絡（PSTN）閘道需求的詳細資料，請參閱規劃檔中的 lync server 2013 中的[中繼伺服器元件](lync-server-2013-mediation-server-component.md)和 lync server 2013 中的發佈伺服器的[元件與拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md)。

<div>

## <a name="hardware-requirements"></a>硬體需求

因為 web 會議和 A/V 會議是與前端伺服器 collocated，所以伺服器的硬體需求與前端伺服器的需求相同。 如需硬體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。 下列是電話撥入式會議所需的元件，也會有與前端伺服器相同的硬體需求：

  - 應用程式服務

  - 會議助理應用程式

  - 會議公告應用程式

前端伺服器的硬體需求與 Lync Server 2013 中的許多其他伺服器角色相同，如下表所示。

</div>

<div>

## <a name="software-requirements"></a>軟體需求

因為 web 會議和 A/V 會議是與前端伺服器 collocated，所以伺服器軟體需求與前端伺服器的需求相同。 如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。

針對網路會議，Lync Server 2013 也需要 Office Web Apps 和 Office Web Apps 伺服器（先前稱為 WAC 伺服器）來處理 PowerPoint 簡報。 如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

如果是電話撥入式會議、應用程式服務、會議助理應用程式及會議公告應用程式，與前端伺服器的作業系統需求相同。 如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。

會議助理應用程式與會議公告應用程式要求 Windows Media 格式執行時間已安裝在前端伺服器上。 Windows Media 格式執行時間需要播放 Windows Media 音訊（WMA）檔案，這些檔案是用來等候音樂、錄製的名稱和提示。 除了 Windows Server 2012 和 Windows Server 2012 R2 之外，當您執行安裝程式時，Windows Media 格式執行時間會自動安裝為 Windows 桌面體驗的一部分，但您可能需要重新開機電腦。 因此，建議您在 Windows 桌面體驗中安裝，包括 Windows 媒體格式執行時間，然後再執行安裝程式。 Windows Server 2012 和 Windows Server 2012 R2 需要 Microsoft 媒體基礎。

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>電話撥入式會議的埠需求

下表說明電話撥入式會議所使用的埠。 如果您使用負載平衡器，請確定已針對將在池中執行的任何應用程式所使用的埠設定負載平衡器。

這些埠是預設的設定，您可以使用**CsApplicationServer** Cmdlet 變更這些設定。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

<div>


> [!NOTE]  
> 池中相同應用程式的所有實例都使用相同的 SIP 偵聽埠。



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>電話撥入式會議所用的埠

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>埠號碼</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>由會議助理應用程式用於 SIP 偵聽要求</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>由會議公告應用程式用於 SIP 偵聽要求</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>電話撥入式會議支援的用戶端

您可以使用下列用戶端來排程支援撥入存取的內部部署會議：

  - Lync 2013 的線上會議增益集（安裝 Lync 2013 或出席者時會自動安裝）

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>電話撥入式會議設定頁面需求

[電話撥入式會議設定] 頁面支援下表所述的作業系統與網頁瀏覽器混合。

<div>


> [!NOTE]  
> 支援32位及64位版本的作業系統。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>支援的作業系統與網頁瀏覽器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>作業系統</th>
<th>網頁瀏覽器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>電話撥入式會議的音訊檔需求

Lync Server 2013 不支援自訂語音提示和電話撥入式會議的音樂。 不過，如果您需要變更預設音訊檔案，請參閱 Microsoft 知識庫文章961177，[說明如何在 Microsoft Office 通訊伺服器 2007 R2 中自訂語音提示或音樂檔案，以進行電話撥入式音訊會議](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)。

您也可以使用[Microsoft Lync Server 會議助理自訂語音提示](http://go.microsoft.com/fwlink/p/?linkid=396880)管理實用程式，當電話來電者加入 Lync 會議時，系統會使用自訂提示來取代預設語音提示，以提供不同的會議進入體驗。 您可以在執行 Lync Server 2010 或 Lync Server 2013 （企業版或標準版）的伺服器上安裝自訂語音提示。

會議助理應用程式與會議公告應用程式對於保留的音樂、錄製的名稱及音訊提示檔案有下列需求：

  - Windows Media 音訊（WMA）檔案格式

  - 16位 mono

  - 48 kbps 2-pass CBR （恒定傳輸率）

  - 24DB 的語音層級

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>電話撥入式會議的使用者需求

電話撥入式會議使用者必須有指派給其帳戶的唯一電話號碼或副檔名。 此需求支援在電話撥入式會議期間進行驗證。 企業使用者（也就是在貴組織內擁有 Active Directory 網域服務認證和 Lync Server 帳戶的使用者）輸入他們的電話號碼（或分機），以及使用個人識別碼（PIN）撥入會議作為已驗證使用者。

</div>

</div>

<span> </span>

</div>

</div>

</div>

