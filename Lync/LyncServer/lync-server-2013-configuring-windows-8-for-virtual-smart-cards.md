---
title: Lync Server 2013：設定虛擬智慧卡的 Windows 8
description: Lync Server 2013：設定 Windows 8 的虛擬智慧卡。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112047f91a20dd552c628fb33eba7bb9ad3d0f01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542159"
---
# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="cbf75-103">設定使用虛擬智慧卡搭配 Lync Server 2013 的 Windows 8</span><span class="sxs-lookup"><span data-stu-id="cbf75-103">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbf75-104">_**主題上次修改日期：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="cbf75-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="cbf75-105">部署雙因素驗證和智慧卡技術時，要考慮的一個因素是實施成本。</span><span class="sxs-lookup"><span data-stu-id="cbf75-105">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="cbf75-106">Windows 8 提供許多新的安全性功能，其中一個最有意思的新功能是支援虛擬智慧卡。</span><span class="sxs-lookup"><span data-stu-id="cbf75-106">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="cbf75-107">針對配備受信任平臺模組的電腦 (符合規格版本1.2 的 TPM) 晶片，組織現在可以取得智慧卡登入的優勢，而不需要在硬體上進行任何額外的投資。</span><span class="sxs-lookup"><span data-stu-id="cbf75-107">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="cbf75-108">如需詳細資訊，請參閱搭配 Windows 8 使用虛擬智慧卡 [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365) 。</span><span class="sxs-lookup"><span data-stu-id="cbf75-108">For more information, see Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="cbf75-109">設定虛擬智慧卡的 Windows 8</span><span class="sxs-lookup"><span data-stu-id="cbf75-109">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="cbf75-110">使用啟用 Lync 功能之使用者的認證登入 Windows 8 電腦。</span><span class="sxs-lookup"><span data-stu-id="cbf75-110">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="cbf75-111">在 [Windows 8 開始] 畫面上，將游標移至螢幕的右下角。</span><span class="sxs-lookup"><span data-stu-id="cbf75-111">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="cbf75-112">選取 [ **搜尋** ] 選項，然後搜尋 [ **命令提示**字元]。</span><span class="sxs-lookup"><span data-stu-id="cbf75-112">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="cbf75-113">在 **命令提示**字元上按一下滑鼠右鍵，然後選取 [ **以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="cbf75-113">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="cbf75-114">執行下列命令，以 (TPM) 管理主控台開啟受信任的平臺模組：</span><span class="sxs-lookup"><span data-stu-id="cbf75-114">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="cbf75-115">在 [TPM 管理主控台] 中，確認您的 TPM 規格版本至少是1。2</span><span class="sxs-lookup"><span data-stu-id="cbf75-115">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cbf75-116">如果您收到的對話方塊指出無法找到相容的信任平臺模組 (TPM) ，請確認該電腦具有相容的 TPM 模組，且已在系統 BIOS 中啟用。</span><span class="sxs-lookup"><span data-stu-id="cbf75-116">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="cbf75-117">關閉 TPM 管理主控台</span><span class="sxs-lookup"><span data-stu-id="cbf75-117">Close the TPM management console</span></span>

8.  <span data-ttu-id="cbf75-118">在命令提示字元處，使用下列命令建立新的虛擬智慧卡：</span><span class="sxs-lookup"><span data-stu-id="cbf75-118">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cbf75-119">若要在建立虛擬智慧卡時提供自訂 PIN 碼值，請改用/pin prompt。</span><span class="sxs-lookup"><span data-stu-id="cbf75-119">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="cbf75-120">在命令提示字元中執行下列命令，以開啟 [電腦管理] 主控台：</span><span class="sxs-lookup"><span data-stu-id="cbf75-120">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="cbf75-121">在 [電腦管理] 主控台中，選取 [ **裝置管理**]。</span><span class="sxs-lookup"><span data-stu-id="cbf75-121">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="cbf75-122">展開 [ **智慧卡讀取器**]。</span><span class="sxs-lookup"><span data-stu-id="cbf75-122">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="cbf75-123">確認已成功建立新的虛擬智慧卡讀取器。</span><span class="sxs-lookup"><span data-stu-id="cbf75-123">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

