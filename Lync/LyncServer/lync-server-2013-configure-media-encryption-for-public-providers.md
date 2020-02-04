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
ms.openlocfilehash: 6d4ab36d19726a6092f978a2ac2a119b248cd0f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="9d001-102">在 Lync Server 2013 中設定公用提供者的媒體加密</span><span class="sxs-lookup"><span data-stu-id="9d001-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d001-103">_**主題上次修改日期：** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="9d001-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="9d001-104">如果您是使用 Windows Live Messenger 來實現音訊/視頻（A/V）同盟，您需要修改兩個參數： Lync Server 加密層級與 EnablePublicCloudAccess 原則。</span><span class="sxs-lookup"><span data-stu-id="9d001-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="9d001-105">根據預設，加密層級會設定為 [必要]。</span><span class="sxs-lookup"><span data-stu-id="9d001-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="9d001-106">您必須將此設定變更為 [支援]。</span><span class="sxs-lookup"><span data-stu-id="9d001-106">You must change this setting to Supported.</span></span> <span data-ttu-id="9d001-107">如果 EnablePublicCloudAccess 原則設定為 false，則需要將它設定為**True**。</span><span class="sxs-lookup"><span data-stu-id="9d001-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="9d001-108">您可以從 Lync Server 管理命令介面執行此動作。</span><span class="sxs-lookup"><span data-stu-id="9d001-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="9d001-109">設定適用于 Windows Live 的同盟</span><span class="sxs-lookup"><span data-stu-id="9d001-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="9d001-110">在前端伺服器上啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server Management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="9d001-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9d001-111">在命令提示字元中，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="9d001-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="9d001-112">這是必要步驟，因為 Windows Live Messenger 不支援音訊/視頻加密。</span><span class="sxs-lookup"><span data-stu-id="9d001-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="9d001-113">該命令會將您的全域原則設定為支援加密設定，而不需要加密音訊/視頻資料。</span><span class="sxs-lookup"><span data-stu-id="9d001-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="9d001-114">支援加密的用戶端仍會使用加密，例如 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="9d001-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

