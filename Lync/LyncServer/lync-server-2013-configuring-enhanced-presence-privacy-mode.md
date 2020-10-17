---
title: Lync Server 2013：設定增強型目前狀態隱私權模式
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
ms.openlocfilehash: d9a06a7bf01664c260ace3a86537665e185b64f8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532600"
---
# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>在 Lync Server 2013 中設定增強型目前狀態隱私權模式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-08_

使用增強型目前狀態隱私權模式，使用者可以限制其目前狀態資訊，使其僅對 Lync 2013 連絡人清單中所列的連絡人可見。 **New-CsPrivacyConfiguration**   和**Set-CsPrivacyConfiguration** Cmdlet 的 EnablePrivacyMode 參數會控制此選項。 當 EnablePrivacyMode 設定為 True 時，可在 Lync 2013 的 [狀態] 選項中，將目前狀態資訊限制為 [連絡人] 的選項。 當 EnablePrivacyMode 設定為 False 時，使用者可以選擇無條件允許所有人查看其目前狀態資訊，或遵循管理員對隱私權模式所進行的任何後續變更。

<div>


> [!IMPORTANT]  
> Lync 2013 和 Lync 2010 隱私權設定不會由舊版 Microsoft Office Communicator 2007 R2 或 Microsoft Office Communicator 2007) 所認可 (。 如果允許舊版的 Office Communicator 登入，則未經授權可查看的使用者，Lync 2013 使用者的狀態、聯繫資訊或圖片可能會被使用者查看。 此外，如果您稍後以舊版的 Communicator 登入，則會重設 Lync 2013 使用者的隱私權設定。<BR>基於這些原因，在遷移案例中啟用增強型目前狀態隱私權模式： 
> <UL>
> <LI>
> <P>確定每位使用者都已安裝 Lync 2013。</P>
> <LI>
> <P>定義用戶端版本原則規則，以防止舊版的 Communicator 登入。</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>啟用增強型目前狀態隱私權模式

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列命令：
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    此命令會為組織中目前使用的所有隱私權設定設定啟用隱私權模式。 如需 Lync Server 增強型狀態隱私權模式原則設定如何管理 Lync 2013 用戶端的連絡人顯示狀態的詳細資訊，請參閱 Microsoft 知識庫文章 [啟用 Lync Server 增強顯示狀態隱私權模式會將某些 Lync 連絡人的目前狀態更新為「無法使用](https://support.microsoft.com/kb/3020057)」。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

