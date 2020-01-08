---
title: Lync Server 2013：設定會議加入頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984386eb15aac3c3d2d46c9d7aaab53457915b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>在 Lync Server 2013 中設定會議加入頁面

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-14_

當使用者按一下會議邀請中的會議連結時，會議加入頁面會偵測到 Lync 2013 用戶端是否已安裝在使用者的電腦上。 如果已安裝用戶端，用戶端會開啟並加入會議。 如果未安裝用戶端，則預設會開啟2013版的 Lync Web App。

如果您想要允許使用者使用 Office Communicator 2007 R2 或 Lync 2010 應答加入會議，您可以修改會議加入頁面的行為。 這些設定選項已從 Lync Server 2013 [控制台] 中移除，但您可以使用 CsWebServiceConfiguration Cmdlet 進行設定。

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>會議加入頁面集-CsWebServiceConfiguration 參數

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>CsWebServiceConfiguration 參數</th>
<th>描述</th>
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

2.  若要查看 web 服務設定，請執行下列 Cmdlet：
    
        Get-CsWebServiceConfiguration

3.  根據您的喜好設定（如需此 Cmdlet 之參數的詳細資料，請參閱 Lync Server 2013 管理命令介面檔中的[設定 CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) ），執行下列命令，並將參數設定為 True 或 False。
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>請參閱


[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

