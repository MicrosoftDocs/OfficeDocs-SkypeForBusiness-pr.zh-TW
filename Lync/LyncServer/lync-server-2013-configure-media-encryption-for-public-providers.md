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

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="a4af7-102">在 Lync Server 2013 中設定公用提供者的媒體加密</span><span class="sxs-lookup"><span data-stu-id="a4af7-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4af7-103">_**上次修改主題：** 2014年-12-12_</span><span class="sxs-lookup"><span data-stu-id="a4af7-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="a4af7-104">如果您要實作音訊/視訊 (A / V) 同盟與 Windows Live Messenger，有兩個您要修改的參數： Lync Server 的加密層級與 EnablePublicCloudAccess 原則。</span><span class="sxs-lookup"><span data-stu-id="a4af7-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="a4af7-105">根據預設，加密層級設為必要。</span><span class="sxs-lookup"><span data-stu-id="a4af7-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="a4af7-106">您必須將此設定變更為 [已支援]。</span><span class="sxs-lookup"><span data-stu-id="a4af7-106">You must change this setting to Supported.</span></span> <span data-ttu-id="a4af7-107">如果 EnablePublicCloudAccess 原則設為 false，這必須設為**True**。</span><span class="sxs-lookup"><span data-stu-id="a4af7-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="a4af7-108">您可以從 Lync Server 管理命令介面來這麼做。</span><span class="sxs-lookup"><span data-stu-id="a4af7-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="a4af7-109">設定 Windows Live 的同盟</span><span class="sxs-lookup"><span data-stu-id="a4af7-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="a4af7-110">在前端伺服器上啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="a4af7-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a4af7-111">在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="a4af7-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="a4af7-112">這是必要的步驟，因為 Windows Live Messenger 不支援加密的音訊/視訊。</span><span class="sxs-lookup"><span data-stu-id="a4af7-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="a4af7-113">此命令將您的全域原則設定而不需要加密的音訊/視訊資料支援加密設定。</span><span class="sxs-lookup"><span data-stu-id="a4af7-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="a4af7-114">支援加密的用戶端仍會使用加密，例如 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="a4af7-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

