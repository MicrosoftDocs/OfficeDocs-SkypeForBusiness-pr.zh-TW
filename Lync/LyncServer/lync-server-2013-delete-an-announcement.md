---
title: Lync Server 2013：刪除公告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91a15057e4785a16e7fc632422573ee02d1d920b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a>在 Lync Server 2013 中刪除公告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

使用下列程式來刪除用於呼叫未指派號碼的宣告。

<div>

## <a name="to-delete-an-announcement"></a>刪除公告

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  列出貴組織中的所有宣告。 在命令列上執行：
    
        Get-CsAnnouncement

4.  在產生的清單中，找出您要刪除的宣告，然後複製 GUID。 然後，在命令列上執行：
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    例如：
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > 如需更多選項的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">CsAnnouncement</A>及<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立公告](lync-server-2013-create-an-announcement.md)  


[移除-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

