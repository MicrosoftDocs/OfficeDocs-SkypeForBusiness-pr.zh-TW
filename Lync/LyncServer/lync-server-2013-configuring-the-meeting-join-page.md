---
title: Lync Server 2013： 設定會議加入頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 872e95c1d5254830a80b8a0d0dd84b233f2d1813
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>Lync Server 2013 中設定會議加入頁面

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-12-14_

當使用者按一下會議中的連結會議邀請，會議加入頁面會偵測到使用者的電腦上是否已安裝 Lync 2013 用戶端。 如果已安裝用戶端，則用戶端會開啟並加入會議。 如果未安裝在用戶端，預設的 Lync Web App 2013 版本會開啟。

您可以修改行為的會議加入頁面如果您想要允許使用者加入會議與 Office Communicator 2007 R2 或 Lync 2010 Attendant。 已從 Lync Server 2013 控制台]，移除這些組態選項，但您使用 Set-cswebserviceconfiguration cmdlet 來設定。

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>會議加入頁面 Set-CsWebServiceConfiguration 參數

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Set-CsWebServiceConfiguration 參數</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>如果設為 True，使用以外的 Lync 用戶端應用程式加入會議的使用者將能夠使用 Office Communicator 2007 R2 來加入會議的機會。 預設值為 False。</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>此參數設為 True 時，就會自動擴充參加線上會議的其他選項 (例如 Office Communicator 2007 R2)，並且對使用者顯示。設為 False (預設值) 時，可使用這些選項，但使用者必須自行顯示選項清單。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>若要設定會議加入頁面使用 Lync Server 2013 管理命令介面

1.  啟動 Lync Server 2013 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  如果要檢視 Web 服務組態設定，請執行下列 Cmdlet：
    
        Get-CsWebServiceConfiguration

3.  執行下列命令，參數設為 True 或 False，取決於偏好 （如需此 cmdlet 之參數的詳細資訊，請參閱[Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) Lync Server 2013 管理命令介面文件中）：
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>另請參閱


[Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

