---
title: Lync Server 2013： 設定公用提供者的媒體加密
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f1775a845c10797d145c7ee1ad5def3af729f4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>在 Lync Server 2013 中設定公用提供者的媒體加密

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-12-12_

如果您要實作音訊/視訊 (A / V) 同盟與 Windows Live Messenger，有兩個您要修改的參數： Lync Server 的加密層級與 EnablePublicCloudAccess 原則。 根據預設，加密層級設為必要。 您必須將此設定變更為 [已支援]。 如果 EnablePublicCloudAccess 原則設為 false，這必須設為**True**。 您可以從 Lync Server 管理命令介面來這麼做。

<div>

## <a name="configure-federation-for-windows-live"></a>設定 Windows Live 的同盟

1.  在前端伺服器上啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令提示字元中輸入下列命令：
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 這是必要的步驟，因為 Windows Live Messenger 不支援加密的音訊/視訊。 此命令將您的全域原則設定而不需要加密的音訊/視訊資料支援加密設定。 支援加密的用戶端仍會使用加密，例如 Lync 2013。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

