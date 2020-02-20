---
title: Lync Server 2013： 設定 Windows 8 的虛擬智慧卡
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
ms.openlocfilehash: 29fa0be32f5a2c2a0af0b63dadddda3038675adf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="223a1-102">設定 Windows 8 搭配 Lync Server 2013 使用虛擬智慧卡</span><span class="sxs-lookup"><span data-stu-id="223a1-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="223a1-103">_**上次修改主題：** 2013年-07-03_</span><span class="sxs-lookup"><span data-stu-id="223a1-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="223a1-104">要考慮部署雙因素驗證和智慧卡技術時的一個因素是實作的成本。</span><span class="sxs-lookup"><span data-stu-id="223a1-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="223a1-105">Windows 8 提供了數個新的安全性功能，且下方其中的最重要的新功能為虛擬智慧卡的支援。</span><span class="sxs-lookup"><span data-stu-id="223a1-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="223a1-106">針對配備信任平台模組 (TPM) 晶片符合規格 1.2 版的電腦，組織現在可以取得的優點智慧卡登入但不進行任何額外的投資的硬體。</span><span class="sxs-lookup"><span data-stu-id="223a1-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="223a1-107">如需詳細資訊，請參閱在 Windows 8 與使用虛擬智慧卡[https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365)。</span><span class="sxs-lookup"><span data-stu-id="223a1-107">For more information, see Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="223a1-108">若要設定 Windows 8 的虛擬智慧卡</span><span class="sxs-lookup"><span data-stu-id="223a1-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="223a1-109">使用已啟用 Lync 之使用者的認證，Windows 8 電腦登入。</span><span class="sxs-lookup"><span data-stu-id="223a1-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="223a1-110">在 Windows 8 的 [開始] 畫面上，將游標移至螢幕的右下角。</span><span class="sxs-lookup"><span data-stu-id="223a1-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="223a1-111">選取 [**搜尋**] 選項，然後搜尋**命令提示字元**。</span><span class="sxs-lookup"><span data-stu-id="223a1-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="223a1-112">在**命令提示字元處**上, 按一下滑鼠右鍵，然後選取 [**以管理員身分執行**。</span><span class="sxs-lookup"><span data-stu-id="223a1-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="223a1-113">開啟受信任的平台模組 (TPM) 管理主控台執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="223a1-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="223a1-114">從 [TPM 管理] 主控台中，確認您 TPM 規格版本至少 1.2</span><span class="sxs-lookup"><span data-stu-id="223a1-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="223a1-115">如果您收到表示找不到相容信任平台模組 (TPM)] 對話方塊，請確認電腦沒有相容的 TPM 模組，而且它已啟用系統 bios。</span><span class="sxs-lookup"><span data-stu-id="223a1-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="223a1-116">關閉 TPM 管理主控台</span><span class="sxs-lookup"><span data-stu-id="223a1-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="223a1-117">從命令提示字元處，建立新虛擬智慧卡使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="223a1-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="223a1-118">若要建立虛擬智慧卡時，請提供自訂的 pin 碼值，請改為使用 /pin 提示。</span><span class="sxs-lookup"><span data-stu-id="223a1-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="223a1-119">在命令提示字元中，開啟 [電腦管理] 主控台執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="223a1-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="223a1-120">在 [電腦管理] 主控台中，選取 [**裝置管理**]。</span><span class="sxs-lookup"><span data-stu-id="223a1-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="223a1-121">展開 [**智慧卡讀取者**]。</span><span class="sxs-lookup"><span data-stu-id="223a1-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="223a1-122">請確認已成功建立新的虛擬智慧卡讀取。</span><span class="sxs-lookup"><span data-stu-id="223a1-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

