---
title: Lync Server 2013：設定會議加入頁面
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
ms.openlocfilehash: c191bbc8927790345e7f969c38e4bf1a74ec3bdb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532320"
---
# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>在 Lync Server 2013 中設定會議加入頁面

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-14_

當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面便會偵測使用者電腦上是否已安裝 Lync 2013 用戶端。 如果已安裝用戶端，則用戶端會開啟並加入會議。 若未安裝用戶端，則預設會開啟2013版本的 Lync Web App。

如果您想要允許使用者加入使用 Office Communicator 2007 R2 或 Lync 2010 的會議，您可以修改會議加入頁面的行為。 這些設定選項已從 Lync Server 2013 控制台中移除，但您使用 Set-CsWebServiceConfiguration Cmdlet 進行設定。

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>會議加入頁面 Set-CsWebServiceConfiguration 參數

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Set-CsWebServiceConfiguration 參數</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>若設為 True，使用 Lync 以外的用戶端應用程式加入會議的使用者，將有機會利用 Office Communicator 2007 R2 加入會議。 預設值為 False。</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>此參數設為 True 時，就會自動擴充參加線上會議的其他選項 (例如 Office Communicator 2007 R2)，並且對使用者顯示。設為 False (預設值) 時，可使用這些選項，但使用者必須自行顯示選項清單。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面設定會議加入頁面

1.  啟動 Lync Server 2013 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  如果要檢視 Web 服務組態設定，請執行下列 Cmdlet：
    
        Get-CsWebServiceConfiguration

3.  執行下列命令，並將參數設定為 True 或 False，這取決於您的喜好設定 (如需此 Cmdlet 之參數的詳細資訊，請參閱 Lync Server 2013 管理命令介面檔) 中的 [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) 。
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>另請參閱


[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

