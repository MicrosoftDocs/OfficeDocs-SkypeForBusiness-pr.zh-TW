---
title: 在團隊中接收有關舊版系統的訊息和通話問題
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 針對在舊版系統上接收郵件與通話的相關問題進行疑難排解
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: af7845b5fd6d50d63be6cd21749cbfedc7669fcf
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085149"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="ee19e-103">在舊版系統上接收郵件和通話的問題</span><span class="sxs-lookup"><span data-stu-id="ee19e-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="ee19e-104">如果使用者使用的是較舊版本的小組，或已使用其他應用程式登入，就可能會遇到接收郵件或呼叫的問題。</span><span class="sxs-lookup"><span data-stu-id="ee19e-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="ee19e-105">舊版 ADU 設置</span><span class="sxs-lookup"><span data-stu-id="ee19e-105">Legacy ADU setups</span></span>

 <span data-ttu-id="ee19e-106">如果使用者登入加入網域的電腦，但是您**不希望 Teams 登入畫面預先填入其使用者名稱**，系統管理員可以設定下列 Windows 登錄，關閉預先填入使用者名稱 (UPN) 的功能：</span><span class="sxs-lookup"><span data-stu-id="ee19e-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="ee19e-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="ee19e-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="ee19e-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="ee19e-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="ee19e-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="ee19e-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="ee19e-110">針對以 ".local" 或 ".corp" 結尾的使用者名稱，略過或忽略使用者名稱預先填入的功能依預設會開啟，因此您不需要設定登錄機碼就能關閉此功能。</span><span class="sxs-lookup"><span data-stu-id="ee19e-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="ee19e-111">如需詳細資訊，請參閱[使用新式驗證登入 Microsoft 團隊](sign-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ee19e-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="ee19e-112">Skype 權杖吊銷</span><span class="sxs-lookup"><span data-stu-id="ee19e-112">Skype token revocation</span></span>

<span data-ttu-id="ee19e-113">在變更/重設密碼時，舊版用戶端將不會收到長達一小時的訊息和來電。</span><span class="sxs-lookup"><span data-stu-id="ee19e-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="ee19e-114">若要解決此問題，請重新開機應用程式或移至較新的用戶端。</span><span class="sxs-lookup"><span data-stu-id="ee19e-114">To resolve this issue, either restart the app or move to newer clients.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ee19e-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="ee19e-115">Related topics</span></span>

[<span data-ttu-id="ee19e-116">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="ee19e-116">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)