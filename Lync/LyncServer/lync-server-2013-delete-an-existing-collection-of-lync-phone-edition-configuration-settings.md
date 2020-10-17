---
title: 刪除現有的 Lync Phone Edition 配置設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce796b13ea69296fa72799a13d35cb2046a643b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514630"
---
# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1e124-102">在 Lync Server 2013 中刪除現有的 Lync Phone Edition 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="1e124-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e124-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1e124-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1e124-104">如果您不再想要對執行 Lync Phone Edition 的裝置使用設定集合，請將其刪除。</span><span class="sxs-lookup"><span data-stu-id="1e124-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="1e124-105">若您刪除網站的集合，該網站中的電話就會套用全域設定。</span><span class="sxs-lookup"><span data-stu-id="1e124-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="1e124-106">您無法刪除全域集合。</span><span class="sxs-lookup"><span data-stu-id="1e124-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1e124-107">若您不想刪除集合，而只想變更部分設定。</span><span class="sxs-lookup"><span data-stu-id="1e124-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="1e124-108">如需如何執行此動作的詳細資訊，請參閱 <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">在 Lync Server 2013 中建立或修改 Lync Phone Edition 設定的集合</A>。</span><span class="sxs-lookup"><span data-stu-id="1e124-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="1e124-109">若要刪除 Lync Phone Edition 配置設定的集合</span><span class="sxs-lookup"><span data-stu-id="1e124-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="1e124-110">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1e124-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1e124-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="1e124-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1e124-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="1e124-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1e124-113">在左導覽列中，按一下 [用戶端]\*\*\*\*，然後按一下 [裝置設定]\*\*\*\* 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="1e124-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="1e124-114">在「裝置設定」\*\*\*\* 頁面中，按一下欲刪除的集合，然後按一下 [編輯]\*\*\*\* 功能表，再按一下 [刪除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e124-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1e124-p104">若您要刪除全域集合，設定就會還原為預設值，但集合仍會存在。</span><span class="sxs-lookup"><span data-stu-id="1e124-p104">If you delete the global collection, the settings just revert to the default settings. The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="1e124-117">在確認對話方塊中，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e124-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1e124-118">使用 Windows PowerShell Cmdlet 移除 Lync Phone Edition 設定設定</span><span class="sxs-lookup"><span data-stu-id="1e124-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1e124-119">您可以使用 Windows PowerShell 和 **CsUCConfiguration** 指令程式來刪除 Lync Phone Edition 設定設定。</span><span class="sxs-lookup"><span data-stu-id="1e124-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="1e124-120">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e124-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1e124-121">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="1e124-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="1e124-122">移除指定的 Lync Phone Edition 配置設定集合</span><span class="sxs-lookup"><span data-stu-id="1e124-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="1e124-123">此命令會刪除套用至 Redmond 網站的 UC 電話組態設定：</span><span class="sxs-lookup"><span data-stu-id="1e124-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="1e124-124">若要移除所有套用至網站範圍的 Lync Phone Edition 設定設定</span><span class="sxs-lookup"><span data-stu-id="1e124-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="1e124-125">此命令會移除套用至服務範圍的所有 UC 電話組態設定：</span><span class="sxs-lookup"><span data-stu-id="1e124-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="1e124-126">若要移除已停用電話鎖定的所有 Lync Phone Edition 設定設定</span><span class="sxs-lookup"><span data-stu-id="1e124-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="1e124-127">此命令可刪除已停用電話鎖定的任何 UC 電話組態設定集合：</span><span class="sxs-lookup"><span data-stu-id="1e124-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="1e124-128">如需詳細資訊，請參閱 [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))。</span><span class="sxs-lookup"><span data-stu-id="1e124-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

