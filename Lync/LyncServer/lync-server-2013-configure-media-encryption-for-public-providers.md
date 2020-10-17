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
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="1fa26-102">在 Lync Server 2013 中設定公用提供者的媒體加密</span><span class="sxs-lookup"><span data-stu-id="1fa26-102">Configure media encryption for public providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fa26-103">_**主題上次修改日期：** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="1fa26-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="1fa26-104">如果您正在執行音訊/視頻 (A/V 與 Windows Live Messenger) 同盟，必須修改兩個參數： Lync Server 加密層級和 EnablePublicCloudAccess 原則。</span><span class="sxs-lookup"><span data-stu-id="1fa26-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="1fa26-105">根據預設，加密層級會設定為 [必要]。</span><span class="sxs-lookup"><span data-stu-id="1fa26-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="1fa26-106">您必須將此設定變更為 [已支援]。</span><span class="sxs-lookup"><span data-stu-id="1fa26-106">You must change this setting to Supported.</span></span> <span data-ttu-id="1fa26-107">如果 EnablePublicCloudAccess 原則設定為 false，則必須將它設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="1fa26-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="1fa26-108">您可以從 Lync Server 管理命令介面來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1fa26-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="1fa26-109">設定 Windows Live 的同盟</span><span class="sxs-lookup"><span data-stu-id="1fa26-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="1fa26-110">在前端伺服器上啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1fa26-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1fa26-111">在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="1fa26-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="1fa26-112">這是必要步驟，因為 Windows Live Messenger 不支援音訊/視頻的加密。</span><span class="sxs-lookup"><span data-stu-id="1fa26-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="1fa26-113">命令會將您的全域原則設定為支援加密設定，而不需要加密音訊/視頻資料。</span><span class="sxs-lookup"><span data-stu-id="1fa26-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="1fa26-114">支援加密的用戶端仍會使用加密，例如 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="1fa26-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

