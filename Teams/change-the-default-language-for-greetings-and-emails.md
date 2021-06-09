---
title: 變更問候語和電子郵件的預設語言
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 瞭解如何設定Microsoft Teams商務用 Skype，以使用其他語言作為組織的預設語音信箱問候語。
ms.openlocfilehash: f211a5e160ce05707a454e5100409840e4c781ac
ms.sourcegitcommit: eca3f5e83e4a07be197936db19f539cbfa2c2bd2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52804520"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="f48f0-103">變更問候語和電子郵件的預設語言</span><span class="sxs-lookup"><span data-stu-id="f48f0-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="f48f0-104">如果您是[全域系統管理員，](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)您可以設定商務用 Skype以其他語言播放其預設語音信箱問候語。</span><span class="sxs-lookup"><span data-stu-id="f48f0-104">If you are a [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="f48f0-105">預設系統問候語類似「請為 John Smith 留言」。</span><span class="sxs-lookup"><span data-stu-id="f48f0-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="f48f0-106">在鈴聲之後，請錄製您的訊息。</span><span class="sxs-lookup"><span data-stu-id="f48f0-106">After the tone, please record your message.</span></span> <span data-ttu-id="f48f0-107">錄製完成後，請掛斷或按井號鍵以尋找更多選項。」</span><span class="sxs-lookup"><span data-stu-id="f48f0-107">When you finish recording, hang up, or press the pound key for more options."</span></span>
  
 <span data-ttu-id="f48f0-108">**首先，請閱讀這項重要資訊：**</span><span class="sxs-lookup"><span data-stu-id="f48f0-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="f48f0-109">**可用的語言** 是由貴組織的位置所決定。</span><span class="sxs-lookup"><span data-stu-id="f48f0-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="f48f0-110">例如，如果您的組織位於美國，您可以將預設語言設定為英文或西班牙文。</span><span class="sxs-lookup"><span data-stu-id="f48f0-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="f48f0-111">如果貴組織位於加拿大，您可以選擇英文和法文。</span><span class="sxs-lookup"><span data-stu-id="f48f0-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="f48f0-112">如要瞭解 Teams 和 商務用 Skype 支援的語言清單，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="f48f0-112">For a list of supported languages in Teams and Skype for Business, see the following:</span></span>
  - [<span data-ttu-id="f48f0-113">Microsoft Teams支援的語言</span><span class="sxs-lookup"><span data-stu-id="f48f0-113">Microsoft Teams supported languages</span></span>](languages-for-voicemail-greetings-and-messages.md)
  - [<span data-ttu-id="f48f0-114">商務用 Skype支援的語言</span><span class="sxs-lookup"><span data-stu-id="f48f0-114">Skype for Business supported languages</span></span>](/skypeforbusiness/what-is-phone-system-in-office-365/phone-system-voicemail/languages-for-voicemail-greetings-and-messages)

- <span data-ttu-id="f48f0-115">**變更個別使用者語音信箱問候語和語音信箱訊息的語言。**</span><span class="sxs-lookup"><span data-stu-id="f48f0-115">**Changing languages for individual user's voicemail greeting and voicemail messages.**</span></span> <span data-ttu-id="f48f0-116">您可以變更使用者偏好的語言，這將變更其語音信箱問候語的語言，以及語音信箱中Outlook訊息。</span><span class="sxs-lookup"><span data-stu-id="f48f0-116">You can change the preferred language for users, which will change the language of their voicemail greeting and voicemail messages sent to their Outlook mailbox.</span></span> <span data-ttu-id="f48f0-117">詳細資訊，請參閱如何設定語言和地區設定Microsoft 365[或Office 365。](/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="f48f0-117">For more information, see [How to set language and region settings for Microsoft 365 or Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

  > [!NOTE]
  > <span data-ttu-id="f48f0-118">使用者可以在登錄後透過他們的設定來變更自己的問候語語言。</span><span class="sxs-lookup"><span data-stu-id="f48f0-118">Users can change their own greeting language through their settings after they sign in.</span></span> <span data-ttu-id="f48f0-119">詳細資訊，請參閱變更商務用 Microsoft 365[顯示語言和時區](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="f48f0-119">For more information, see [Change your display language and time zone in Microsoft 365 for Business](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span></span>
  
- <span data-ttu-id="f48f0-120">**您想要錄製外發語音信箱訊息嗎？**</span><span class="sxs-lookup"><span data-stu-id="f48f0-120">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="f48f0-121">請參閱[檢查商務用 Skype和選項](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)。</span><span class="sxs-lookup"><span data-stu-id="f48f0-121">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="f48f0-122">適用于Microsoft Teams - 使用者可以從桌面用戶端設定Teams[語音信箱設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="f48f0-122">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="f48f0-123">**您想要變更語音信箱提示語言嗎？**</span><span class="sxs-lookup"><span data-stu-id="f48f0-123">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="f48f0-124">針對 商務用 Skype - [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) 並選擇提示語言下 **的新語言**。</span><span class="sxs-lookup"><span data-stu-id="f48f0-124">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="f48f0-125">適用于Microsoft Teams - 使用者可以從桌面用戶端設定Teams[語音信箱問候語](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="f48f0-125">For Microsoft Teams - Users can change their voicemail greeting from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="f48f0-126">變更貴組織中每個人的系統語言</span><span class="sxs-lookup"><span data-stu-id="f48f0-126">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="f48f0-127">使用全域系統管理員 [帳戶在](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 中登錄 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。</span><span class="sxs-lookup"><span data-stu-id="f48f0-127">Sign in with your [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="f48f0-128">在系統管理Microsoft 365，選擇 **設定設定**  >    >  **設定檔**。</span><span class="sxs-lookup"><span data-stu-id="f48f0-128">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span>

     ![螢幕擷取畫面顯示設定選擇組織設定檔。](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="f48f0-130">選擇 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="f48f0-130">Choose **Edit**.</span></span>

    ![顯示編輯選項的螢幕擷取畫面。](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="f48f0-132">從貴組織中每個人的 **偏好語言** 清單中選取語言。</span><span class="sxs-lookup"><span data-stu-id="f48f0-132">Select a language from the **Preferred language** list for everyone in your organization.</span></span>

5. <span data-ttu-id="f48f0-133">選擇 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="f48f0-133">Choose **Save**.</span></span>

## <a name="related-articles-for-the-admin"></a><span data-ttu-id="f48f0-134">適用于系統管理員的相關文章</span><span class="sxs-lookup"><span data-stu-id="f48f0-134">Related articles for the admin</span></span>

- [<span data-ttu-id="f48f0-135">電話系統和通話方案</span><span class="sxs-lookup"><span data-stu-id="f48f0-135">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="f48f0-136">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="f48f0-136">Set up Calling Plans</span></span>](set-up-calling-plans.md)

- [<span data-ttu-id="f48f0-137">在 電話系統中Microsoft 365或Office 365內部部署 PSTN 連接商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="f48f0-137">Plan Phone System in Microsoft 365 or Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)

## <a name="related-topics"></a><span data-ttu-id="f48f0-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="f48f0-138">Related topics</span></span>

- [<span data-ttu-id="f48f0-139">變更商務用或商務用 Microsoft 365 Office 365顯示語言和時區</span><span class="sxs-lookup"><span data-stu-id="f48f0-139">Change your display language and time zone in Microsoft 365 or Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)

- <span data-ttu-id="f48f0-140">[在 2010 及Office新增語言或設定語言喜好設定) ](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="f48f0-140">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>

- [<span data-ttu-id="f48f0-141">啟用或變更鍵盤配置語言</span><span class="sxs-lookup"><span data-stu-id="f48f0-141">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
