---
title: 使用 Microsoft 365 系統管理中心建立資源帳戶
description: 如果您喜歡使用圖形使用者介面，您可以使用 Microsoft 365 系統管理中心為 microsoft 團隊聊天室和共同作業橫條圖建立資源帳戶。
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: 建立裝置帳戶、Microsoft 365 UI、Microsoft 365 系統管理中心
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
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a><span data-ttu-id="d9d2e-104">使用 Microsoft 365 系統管理中心建立 Microsoft 365 資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d9d2e-104">Create a Microsoft 365 resource account using the Microsoft 365 admin center</span></span>

<span data-ttu-id="d9d2e-105">Microsoft 365 資源帳戶是專門用於特定資源（例如房間、投影機等）的信箱和小群組帳戶。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-105">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="d9d2e-106">這些資源帳戶可以使用您在建立規則時所定義的規則，自動回應會議邀請。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-106">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="d9d2e-107">例如，如果您有共同的資源（例如會議室），您可以設定該會議室的資源帳戶，以根據其行事曆可用性來自動接受或拒絕會議邀請。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-107">For example, if you have a common resource such as a conference room, you can set up a resource account for that conference room that will automatically accept or decline meeting invites depending on its calendar availability.</span></span>

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a><span data-ttu-id="d9d2e-108">授權</span><span class="sxs-lookup"><span data-stu-id="d9d2e-108">Licensing</span></span>

<span data-ttu-id="d9d2e-109">在您建立 Microsoft 365 資源帳戶之前，請先檢查其所需的授權類型。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-109">Before you create a Microsoft 365 resource account, check to see what kind of license it needs.</span></span> <span data-ttu-id="d9d2e-110">如果您只使用資源帳戶來預訂資源（也就是將資源邀請到會議，並自動接受或拒絕邀請），您不需要指派授權給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-110">If you'll only use a resource account to book a resource (that is, invite the resource to your meeting and have it automatically accept or decline the invitation), you don't need to assign a license to a resource account.</span></span> <span data-ttu-id="d9d2e-111">在下列情況下，您必須將授權指派給資源帳戶：</span><span class="sxs-lookup"><span data-stu-id="d9d2e-111">You'll need to assign a license to the resource account in the following situations:</span></span>

- <span data-ttu-id="d9d2e-112">**團隊會議**如果您想要將資源（例如 Microsoft 團隊聊天室中的 [共同作業] 列等）加入小組會議，讓出席者能透過它來呈現影片和音訊，您需要會議室授權。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-112">**Teams meeting** If you want the resource (such as a Microsoft Teams Rooms console, collaboration bar, and so on) to join a Teams meeting so attendees can use it to present video and audio through it, you need a Meeting Room license.</span></span> 
- <span data-ttu-id="d9d2e-113">**PSTN 通話**如果您想要資源撥打或接聽外部電話號碼或撥打電話（稱為公用交換電話網絡或 PSTN 通話），您需要 Microsoft 365 手機系統或 Microsoft 365 商務語音授權。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-113">**PSTN calls** If you want the resource to make or receive calls to or from an external phone numbers (called a Public Switched Telephone Network or PSTN call), you need a Microsoft 365 Phone System or Microsoft 365 Business Voice license.</span></span>

<span data-ttu-id="d9d2e-114">如需會議室、手機系統和商務語音授權的詳細資訊，請參閱[Microsoft 團隊附加元件授權](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="d9d2e-114">For more information about Meeting Room, Phone System, and Business Voice licenses, see [Microsoft Teams add-on licenses](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a><span data-ttu-id="d9d2e-115">在 Microsoft 365 系統管理中心建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d9d2e-115">Create a resource account in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="d9d2e-116">透過造訪登入 Microsoft 365https://admin.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d9d2e-116">Sign in to Microsoft 365 by visiting https://admin.microsoft.com</span></span>
2. <span data-ttu-id="d9d2e-117">提供 Microsoft 365 租使用者的管理員認證。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-117">Provide the admin credentials for your Microsoft 365 tenant.</span></span> <span data-ttu-id="d9d2e-118">這會將您帶到您的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-118">This will take you to your Microsoft 365 admin center.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 系統管理中心":::
3. <span data-ttu-id="d9d2e-120">在系統管理中心中，流覽至左面板中的 [**資源**] （您可能需要先選取 [**全部顯示**]），然後選取 [**會議室] & 裝置**]。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-120">In the admin center, navigate to **Resources** in the left panel (you might need to select **Show all** first), and then select **Rooms & equipment**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 系統管理中心-資源":::
4. <span data-ttu-id="d9d2e-122">選取 [**新增資源信箱**] 來建立新的聊天室帳戶。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-122">Select **Add a resource mailbox** to create a new room account.</span></span> <span data-ttu-id="d9d2e-123">輸入帳戶的顯示名稱和電子郵件地址，選取 [**新增**]，然後選取 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-123">Enter a display name and email address for the account, select **Add**, and then select **Close**.</span></span> <span data-ttu-id="d9d2e-124">我們建議您將所有資源帳戶的命名慣例標準化。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-124">We recommend you standardize on a naming convention for all of your resource accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="d9d2e-125">根據預設，資源帳戶是使用下列設定來設定。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-125">By default, resource accounts are set up with the following settings.</span></span> <span data-ttu-id="d9d2e-126">如果您想要變更，請選取 [**設定排程選項**]，然後選取 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-126">If you want to change them, select **Set scheduling options** before you select **Close**.</span></span> <span data-ttu-id="d9d2e-127">如果您稍後想要變更，請流覽至 [**資源**  >  **室 & 裝置**]，選取資源帳戶，然後選取 [**預定選項**] 底下的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-127">If you want to change them later, navigate to **Resources** > **Rooms & equipment**, select the resource account and then select **Edit** under **Booking options**.</span></span>
>
> - <span data-ttu-id="d9d2e-128">允許重複會議</span><span class="sxs-lookup"><span data-stu-id="d9d2e-128">Allow repeat meetings</span></span>
> - <span data-ttu-id="d9d2e-129">自動謝絕超出下列限制的會議</span><span class="sxs-lookup"><span data-stu-id="d9d2e-129">Automatically decline meetings outside of the following limits</span></span>
>   - <span data-ttu-id="d9d2e-130">預定視窗（天）：180</span><span class="sxs-lookup"><span data-stu-id="d9d2e-130">Booking window (days): 180</span></span>
>   - <span data-ttu-id="d9d2e-131">最大持續時間（小時）：24</span><span class="sxs-lookup"><span data-stu-id="d9d2e-131">Maximum duration (hours): 24</span></span>
> - <span data-ttu-id="d9d2e-132">自動接受會議邀請</span><span class="sxs-lookup"><span data-stu-id="d9d2e-132">Auto accept meeting requests</span></span>

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 系統管理中心-新增資源":::
5. <span data-ttu-id="d9d2e-134">流覽至系統管理中心的 [**使用者**] 區段，然後在 [作用中的**使用者**] 清單中，您會看到您剛建立的聊天室。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-134">Navigate to the **Users** section in admin center and, in the **Active users** list, you will see the room you just created.</span></span>

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 系統管理中心-請參閱作用中的使用者":::
6. <span data-ttu-id="d9d2e-136">選取聊天室的名稱，[帳戶屬性] 面板會出現在右側。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-136">Select on the name of the room and an account properties panel will appear on the right.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 系統管理中心-使用者屬性":::
7. <span data-ttu-id="d9d2e-138">現在，您需要指派密碼給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-138">Now you need to assign a password to the resource account.</span></span> <span data-ttu-id="d9d2e-139">在面板中，您可以看到 [帳戶] 屬性及幾個選擇性動作。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-139">In the panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="d9d2e-140">選取 [使用者名稱] 底下的 [**重設密碼**金鑰] 圖示，即可變更密碼。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-140">Select the **Reset password** key icon under the username to change the password.</span></span> <span data-ttu-id="d9d2e-141">取消選取 [**要求此使用者在第一次登入時變更密碼**]。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-141">Unselect **Require this user to change their password when they first sign in**.</span></span> <span data-ttu-id="d9d2e-142">無法透過裝置登入程式變更密碼。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-142">It is not possible to change the password via the device sign-in process.</span></span> <span data-ttu-id="d9d2e-143">選取 [**重設**]。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-143">Select **Reset**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 系統管理中心-重設密碼":::
8. <span data-ttu-id="d9d2e-145">在 [**授權及應用程式**] 區段中，將 [**選取位置**] 設定為將安裝裝置的國家或地區。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-145">In the **Licenses and Apps** section, set **Select location** to the country or region where the device will be installed.</span></span> <span data-ttu-id="d9d2e-146">向下滾動並選取要指派之授權旁邊的方塊（例如 [會議室]），然後選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-146">Scroll down and check the box next to the license to be assigned - such as Meeting Room - and then select **Save changes**.</span></span> <span data-ttu-id="d9d2e-147">授權可能會根據您的組織而有所不同。</span><span class="sxs-lookup"><span data-stu-id="d9d2e-147">The license may vary depending on your organization.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 系統管理中心-指派授權":::
