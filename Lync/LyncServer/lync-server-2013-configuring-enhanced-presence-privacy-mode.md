---
title: Lync Server 2013：設定增強的目前狀態隱私權模式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cc68ad4e3200a268a2a6ea901167f211942c015
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>在 Lync Server 2013 中設定增強的目前狀態隱私權模式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-08_

使用者可以使用增強的目前狀態隱私權模式，限制其目前狀態資訊，使其只對 Lync 2013 連絡人清單中所列的連絡人可見。 **新的-CsPrivacyConfiguration** 和**CsPrivacyConfiguration** Cmdlet 都有一個 EnablePrivacyMode 參數控制此選項。 當 EnablePrivacyMode 設定為 True 時，會在 Lync 2013 狀態選項中，將目前狀態資訊限制為連絡人的選項。 當 EnablePrivacyMode 設定為 False 時，使用者可以選擇 [永遠允許所有人查看其目前狀態資訊]，或遵循系統管理員對隱私權模式所做的任何後續變更。

<div>


> [!IMPORTANT]  
> 早期版本（Microsoft Office Communicator 2007 R2 或 Microsoft Office Communicator 2007）不會遵守 lync 2013 和 Lync 2010 隱私權設定。 如果允許舊版 Office Communicator 登入，Lync 2013 使用者的狀態、連絡人資訊或圖片可能會被未經授權即可查看的人員所查看。 此外，如果 Lync 2013 使用者的隱私權設定稍後以舊版 Communicator 登入，就會重設。<BR>基於這些原因，在遷移案例中，在您啟用 [增強的目前狀態隱私權模式] 之前： 
> <UL>
> <LI>
> <P>確定每位使用者都安裝了 Lync 2013。</P>
> <LI>
> <P>定義用戶端版本原則規則，以防止舊版 Communicator 登入。</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>啟用增強的目前狀態隱私權模式

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列命令：
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    這個命令會針對組織中目前使用的所有隱私權設定啟用 [隱私權模式]。 如需有關 Lync Server 增強的目前狀態隱私權模式原則配置如何管理 Lync 2013 用戶端連絡人目前狀態的詳細資訊，請參閱 Microsoft 知識庫文章[啟用 Lync Server 增強的目前狀態隱私權模式將某些 Lync 連絡人的目前狀態更新為「無法使用](http://support.microsoft.com/kb/3020057)」。

</div>

<div>

## <a name="see-also"></a>請參閱


[CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[新-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

