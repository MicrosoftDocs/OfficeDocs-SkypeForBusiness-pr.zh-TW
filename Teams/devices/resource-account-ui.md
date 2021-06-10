---
title: 使用系統管理中心建立Microsoft 365帳戶
description: 如果您想要使用圖形使用者介面，您可以使用系統管理中心，為Microsoft Teams 會議室和共同Microsoft Teams建立資源Microsoft 365帳戶。
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: 建立裝置帳戶、Microsoft 365 UI，Microsoft 365系統管理中心
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268020"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a><span data-ttu-id="d27f3-104">使用 Microsoft 365 系統管理中心建立Microsoft 365資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d27f3-104">Create a Microsoft 365 resource account using the Microsoft 365 admin center</span></span>

<span data-ttu-id="d27f3-105">Microsoft 365資源帳戶是專門Teams資源 ，例如會議室、投影機等的信箱和信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="d27f3-105">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="d27f3-106">這些資源帳戶可以使用您建立會議邀請時定義的規則，自動回應會議邀請。</span><span class="sxs-lookup"><span data-stu-id="d27f3-106">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="d27f3-107">例如，如果您有一般資源 ，例如會議室，您可以為會議室設定資源帳戶，根據會議室的日曆可用性，自動接受或拒絕會議邀請。</span><span class="sxs-lookup"><span data-stu-id="d27f3-107">For example, if you have a common resource such as a conference room, you can set up a resource account for that conference room that will automatically accept or decline meeting invites depending on its calendar availability.</span></span>

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a><span data-ttu-id="d27f3-108">授權</span><span class="sxs-lookup"><span data-stu-id="d27f3-108">Licensing</span></span>

<span data-ttu-id="d27f3-109">在建立資源Microsoft 365帳戶之前，請檢查它所需的授權類型。</span><span class="sxs-lookup"><span data-stu-id="d27f3-109">Before you create a Microsoft 365 resource account, check to see what kind of license it needs.</span></span> <span data-ttu-id="d27f3-110">如果您只會使用資源帳戶預約資源 (，請邀請資源加入您的會議，並自動接受或拒絕邀請) ，則不需要指派授權給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d27f3-110">If you'll only use a resource account to book a resource (that is, invite the resource to your meeting and have it automatically accept or decline the invitation), you don't need to assign a license to a resource account.</span></span> <span data-ttu-id="d27f3-111">您必須在下列情況下指派授權給資源帳戶：</span><span class="sxs-lookup"><span data-stu-id="d27f3-111">You'll need to assign a license to the resource account in the following situations:</span></span>

- <span data-ttu-id="d27f3-112">**Teams會議** 如果您希望資源 (例如 Microsoft Teams 會議室 主機、共同合作欄等) 加入 Teams 會議，讓出席者能夠透過會議來展示視音訊，您需要 會議室 授權。</span><span class="sxs-lookup"><span data-stu-id="d27f3-112">**Teams meeting** If you want the resource (such as a Microsoft Teams Rooms console, collaboration bar, and so on) to join a Teams meeting so attendees can use it to present video and audio through it, you need a Meeting Room license.</span></span> 
- <span data-ttu-id="d27f3-113">**PSTN 通話** 如果您希望資源撥打或接聽外部電話號碼 (稱為公用交換電話網絡或 PSTN 電話) ，您需要授權Microsoft 365 電話系統或Microsoft 365 商務語音授權。</span><span class="sxs-lookup"><span data-stu-id="d27f3-113">**PSTN calls** If you want the resource to make or receive calls to or from an external phone numbers (called a Public Switched Telephone Network or PSTN call), you need a Microsoft 365 Phone System or Microsoft 365 Business Voice license.</span></span>

<span data-ttu-id="d27f3-114">若要進一會議室、電話系統商務語音授權，[請參閱Microsoft Teams附加元件授權](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="d27f3-114">For more information about Meeting Room, Phone System, and Business Voice licenses, see [Microsoft Teams add-on licenses](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a><span data-ttu-id="d27f3-115">在系統管理中心Microsoft 365資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d27f3-115">Create a resource account in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="d27f3-116">請流覽以Microsoft 365至https://admin.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d27f3-116">Sign in to Microsoft 365 by visiting https://admin.microsoft.com</span></span>
2. <span data-ttu-id="d27f3-117">為您的租使用者提供Microsoft 365認證。</span><span class="sxs-lookup"><span data-stu-id="d27f3-117">Provide the admin credentials for your Microsoft 365 tenant.</span></span> <span data-ttu-id="d27f3-118">這會將您帶至您的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="d27f3-118">This will take you to your Microsoft 365 admin center.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365系統管理中心":::
3. <span data-ttu-id="d27f3-120">在系統管理中心中，流覽至左側面板中的資源 (您可能需要選取顯示所有第一個) ，然後選取會議室&**設備**。 </span><span class="sxs-lookup"><span data-stu-id="d27f3-120">In the admin center, navigate to **Resources** in the left panel (you might need to select **Show all** first), and then select **Rooms & equipment**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365系統管理中心 - 資源":::
4. <span data-ttu-id="d27f3-122">選取 **新增資源信箱** 以建立新的會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="d27f3-122">Select **Add a resource mailbox** to create a new room account.</span></span> <span data-ttu-id="d27f3-123">輸入帳戶的顯示名稱和電子郵件地址，選取 **新增**， **然後選取** 關閉 。</span><span class="sxs-lookup"><span data-stu-id="d27f3-123">Enter a display name and email address for the account, select **Add**, and then select **Close**.</span></span> <span data-ttu-id="d27f3-124">我們建議您將所有資源帳戶的命名慣例標準化。</span><span class="sxs-lookup"><span data-stu-id="d27f3-124">We recommend you standardize on a naming convention for all of your resource accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="d27f3-125">根據預設，資源帳戶會設定為下列設定。</span><span class="sxs-lookup"><span data-stu-id="d27f3-125">By default, resource accounts are set up with the following settings.</span></span> <span data-ttu-id="d27f3-126">如果您想要變更，請選取設定 **排程** 選項， **然後再選取** 關閉 。</span><span class="sxs-lookup"><span data-stu-id="d27f3-126">If you want to change them, select **Set scheduling options** before you select **Close**.</span></span> <span data-ttu-id="d27f3-127">如果您想要稍後變更，請流覽至資源會議室&設備，選取資源帳戶，然後選取在預約選項下  >  \*\*\*\*\*\*編輯\*\*。 </span><span class="sxs-lookup"><span data-stu-id="d27f3-127">If you want to change them later, navigate to **Resources** > **Rooms & equipment**, select the resource account and then select **Edit** under **Booking options**.</span></span>
>
> - <span data-ttu-id="d27f3-128">允許重複會議</span><span class="sxs-lookup"><span data-stu-id="d27f3-128">Allow repeat meetings</span></span>
> - <span data-ttu-id="d27f3-129">自動拒絕下列限制以外的會議</span><span class="sxs-lookup"><span data-stu-id="d27f3-129">Automatically decline meetings outside of the following limits</span></span>
>   - <span data-ttu-id="d27f3-130">預定視窗 (天) ：180</span><span class="sxs-lookup"><span data-stu-id="d27f3-130">Booking window (days): 180</span></span>
>   - <span data-ttu-id="d27f3-131">最長 (小時) ：24</span><span class="sxs-lookup"><span data-stu-id="d27f3-131">Maximum duration (hours): 24</span></span>
> - <span data-ttu-id="d27f3-132">自動接受會議邀請</span><span class="sxs-lookup"><span data-stu-id="d27f3-132">Auto accept meeting requests</span></span>

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365系統管理中心 - 新增資源":::
5. <span data-ttu-id="d27f3-134">流覽 **至系統管理** 中心的使用者區段，並在活動使用者清單中，看到您剛剛建立聊天室。</span><span class="sxs-lookup"><span data-stu-id="d27f3-134">Navigate to the **Users** section in admin center and, in the **Active users** list, you will see the room you just created.</span></span>

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365系統管理中心 - 查看使用中使用者":::
6. <span data-ttu-id="d27f3-136">選取會議室名稱，右側會顯示帳戶屬性面板。</span><span class="sxs-lookup"><span data-stu-id="d27f3-136">Select on the name of the room and an account properties panel will appear on the right.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365系統管理中心 - 使用者屬性":::
7. <span data-ttu-id="d27f3-138">現在您需要為資源帳戶指派密碼。</span><span class="sxs-lookup"><span data-stu-id="d27f3-138">Now you need to assign a password to the resource account.</span></span> <span data-ttu-id="d27f3-139">在面板中，您可以看見帳戶屬性和數個選擇性動作。</span><span class="sxs-lookup"><span data-stu-id="d27f3-139">In the panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="d27f3-140">選取使用者 **名稱下的** 重設密碼鍵圖示以變更密碼。</span><span class="sxs-lookup"><span data-stu-id="d27f3-140">Select the **Reset password** key icon under the username to change the password.</span></span> <span data-ttu-id="d27f3-141">取消選擇 **：要求此使用者第一次登出時變更密碼**。</span><span class="sxs-lookup"><span data-stu-id="d27f3-141">Unselect **Require this user to change their password when they first sign in**.</span></span> <span data-ttu-id="d27f3-142">無法透過裝置登錄程式變更密碼。</span><span class="sxs-lookup"><span data-stu-id="d27f3-142">It is not possible to change the password via the device sign-in process.</span></span> <span data-ttu-id="d27f3-143">選取 **重設**。</span><span class="sxs-lookup"><span data-stu-id="d27f3-143">Select **Reset**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365系統管理中心 - 重設密碼":::
8. <span data-ttu-id="d27f3-145">In the **Licenses and Apps** section, set **Select location** to the country or region where the device will be installed.</span><span class="sxs-lookup"><span data-stu-id="d27f3-145">In the **Licenses and Apps** section, set **Select location** to the country or region where the device will be installed.</span></span> <span data-ttu-id="d27f3-146">向下卷起並選取要指派之授權旁的方塊 ，例如 會議室 ，然後選取儲存 **變更**。</span><span class="sxs-lookup"><span data-stu-id="d27f3-146">Scroll down and check the box next to the license to be assigned - such as Meeting Room - and then select **Save changes**.</span></span> <span data-ttu-id="d27f3-147">授權可能會視貴組織而異。</span><span class="sxs-lookup"><span data-stu-id="d27f3-147">The license may vary depending on your organization.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365系統管理中心 - 指派授權":::
