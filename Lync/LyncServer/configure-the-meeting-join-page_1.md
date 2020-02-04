---
title: 設定會議加入頁面
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 104f5a06395de236c280d083e6211decaaa62b35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>設定會議加入頁面

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-14_

當使用者按一下會議邀請中的會議連結時，會議加入頁面會偵測到 Lync 2013 用戶端是否已安裝在使用者的電腦上。 如果已安裝用戶端，該用戶端會開啟並加入會議。 如果未安裝用戶端，則預設會開啟2013版的 Microsoft Lync Web App。

如果您想要允許使用者使用 Office Communicator 2007 R2 或 Lync 2010 應答加入會議，您可以修改會議加入頁面的行為。 這些設定選項已從 Lync Server 2013 [控制台] 中移除，但您可以使用 CsWebServiceConfiguration Cmdlet 進行設定。

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>會議加入頁面 CsWebServiceConfiguration 參數

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>CsWebServiceConfiguration 參數</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>如果設為 True，則使用 Lync 以外的用戶端應用程式加入會議的使用者將有機會使用 Office Communicator 2007 R2 加入會議。 預設值為 False。</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>當設定為 True 時，加入線上會議的替代選項（例如 Office Communicator 2007 R2）將會自動展開並向使用者顯示。 當設定為 False （預設值）時，這些選項將可供使用，但使用者將必須針對自己顯示選項清單。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面設定會議加入頁面

1.  啟動 Lync Server 2013 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server Management Shell**]。

2.  執行下列 Cmdlet：
    
        Get-CsWebServiceConfiguration
    
    這個 Cmdlet 會傳回 web 服務配置設定。

3.  根據您的喜好設定（如需此 Cmdlet 之參數的詳細資料，請參閱 Lync Server 2013 管理命令介面檔），執行下列命令，並將參數設定為 True 或 False。
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

