---
title: Lync Server 2013：自訂通話駐留等候音樂
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18f7ac9793c8275caa20725d2d303c5fca7f534f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516710"
---
# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a>在 Lync Server 2013 中自訂通話駐留的等候音樂

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-10_

您可以指定您自己的音樂檔案，以用於保留等候音樂，而不是 Lync Server 2013 隨附的預設音樂檔。 如要自訂等候音樂，請使用 **Set-CsCallParkServiceMusicOnHoldFile** Cmdlet。

<div>


> [!NOTE]  
> 如果您自訂等候音樂，且想要將相同的音樂用於多個網站，則必須為每個執行通話駐留應用程式的網站設定音樂檔。



</div>

<div>

## <a name="to-customize-the-music-file"></a>自訂音樂檔案

1.  以 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > 使用 <STRONG>Get-CsService</STRONG> Cmdlet 來識別服務。 如需詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>。

    
    </div>
    
    下列範例顯示如何取得檔案 soothingmusic.wma 的位元組陣列內容，並將其指派給變數。 然後將音訊檔案指派為通話駐留時的等候音樂檔案。 如需詳細資訊，請參閱 [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)。
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a>另請參閱


[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

