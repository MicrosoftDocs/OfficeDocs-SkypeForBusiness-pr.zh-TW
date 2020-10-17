---
title: Lync Server 2013：設定公用提供者的媒體加密
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
ms.openlocfilehash: 45a6a3dcccc766e9905017c0b35949ab4ff6894d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520600"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>在 Lync Server 2013 中設定公用提供者的媒體加密

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-12_

如果您正在執行音訊/視頻 (A/V 與 Windows Live Messenger) 同盟，必須修改兩個參數： Lync Server 加密層級和 EnablePublicCloudAccess 原則。 根據預設，加密層級會設定為 [必要]。 您必須將此設定變更為 [已支援]。 如果 EnablePublicCloudAccess 原則設定為 false，則必須將它設定為 **True**。 您可以從 Lync Server 管理命令介面來執行此動作。

<div>

## <a name="configure-federation-for-windows-live"></a>設定 Windows Live 的同盟

1.  在前端伺服器上啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令提示字元中輸入下列命令：
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 這是必要步驟，因為 Windows Live Messenger 不支援音訊/視頻的加密。 命令會將您的全域原則設定為支援加密設定，而不需要加密音訊/視頻資料。 支援加密的用戶端仍會使用加密，例如 Lync 2013。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

