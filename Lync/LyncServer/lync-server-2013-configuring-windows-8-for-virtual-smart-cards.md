---
title: Lync Server 2013：針對虛擬智慧卡設定 Windows 8
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
ms.openlocfilehash: b6298f7aa6a500a71c0b3732dd2f3d180e7192d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="e8986-102">針對使用 Lync Server 2013 的虛擬智慧卡設定 Windows 8</span><span class="sxs-lookup"><span data-stu-id="e8986-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8986-103">_**主題上次修改日期：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="e8986-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="e8986-104">部署雙因素驗證與智慧卡技術時，要考慮的一個因素是實施成本。</span><span class="sxs-lookup"><span data-stu-id="e8986-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="e8986-105">Windows 8 提供許多新的安全性功能，其中一個最有趣的新功能就是支援虛擬智慧卡。</span><span class="sxs-lookup"><span data-stu-id="e8986-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="e8986-106">對於配備符合規範版本1.2 的可信平臺模組（TPM）晶片的電腦，組織現在可以取得智慧卡登入的優點，而不需要在硬體中進行任何額外的投資。</span><span class="sxs-lookup"><span data-stu-id="e8986-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="e8986-107">如需詳細資訊，請參閱在[http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)Windows 8 中使用虛擬智慧卡。</span><span class="sxs-lookup"><span data-stu-id="e8986-107">For more information, see Using Virtual Smart Cards with Windows 8 at [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="e8986-108">針對虛擬智慧卡設定 Windows 8</span><span class="sxs-lookup"><span data-stu-id="e8986-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="e8986-109">使用啟用 Lync 的使用者認證登入 Windows 8 電腦。</span><span class="sxs-lookup"><span data-stu-id="e8986-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="e8986-110">在 Windows 8 的 [開始] 畫面中，將游標移至畫面的右下角。</span><span class="sxs-lookup"><span data-stu-id="e8986-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="e8986-111">選取 [**搜尋**] 選項，然後搜尋 [**命令提示**字元]。</span><span class="sxs-lookup"><span data-stu-id="e8986-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="e8986-112">以滑鼠右鍵按一下**命令提示**字元，然後選取 [以**系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="e8986-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="e8986-113">執行下列命令以開啟可信平臺模組（TPM）管理主控台：</span><span class="sxs-lookup"><span data-stu-id="e8986-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="e8986-114">從 TPM 管理主控台，確認您的 TPM 規格版本至少為1。2</span><span class="sxs-lookup"><span data-stu-id="e8986-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e8986-115">如果您收到對話方塊，指出找不到相容的信任平臺模組（TPM），請確認電腦有相容的 TPM 模組，且已在系統 BIOS 中啟用。</span><span class="sxs-lookup"><span data-stu-id="e8986-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="e8986-116">關閉 TPM 管理主控台</span><span class="sxs-lookup"><span data-stu-id="e8986-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="e8986-117">在命令提示字元中，使用下列命令建立新的虛擬智慧卡：</span><span class="sxs-lookup"><span data-stu-id="e8986-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e8986-118">若要在建立虛擬智慧卡時提供自訂 PIN 值，請改為使用/pin 提示。</span><span class="sxs-lookup"><span data-stu-id="e8986-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="e8986-119">在命令提示字元中，執行下列命令以開啟 [電腦管理] 主控台：</span><span class="sxs-lookup"><span data-stu-id="e8986-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="e8986-120">在 [電腦管理] 主控台中，選取 [**裝置管理**]。</span><span class="sxs-lookup"><span data-stu-id="e8986-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="e8986-121">展開 [**智慧卡讀取器**]。</span><span class="sxs-lookup"><span data-stu-id="e8986-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="e8986-122">確認已成功建立新的虛擬智慧卡讀卡機。</span><span class="sxs-lookup"><span data-stu-id="e8986-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

