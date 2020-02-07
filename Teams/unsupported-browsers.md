---
title: Microsoft 團隊在不支援的瀏覽器上的會議
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解團隊如何在不受支援的瀏覽器中支援音訊和影片。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f2fc7ee97a5172a849c14d9ede6d93ffc08d302
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837253"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="f438f-103">Microsoft 團隊在不支援的瀏覽器上的會議</span><span class="sxs-lookup"><span data-stu-id="f438f-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="f438f-104">某些瀏覽器（例如 Internet Explorer 11、Safari 和 Firefox）支援 Microsoft 團隊 web app，但不支援某些小組通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="f438f-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="f438f-105">若要解決這個限制，小組 web 應用程式可讓使用者透過 PSTN 連線接收音訊，並讓他們以降低的顯示速率來查看已顯示的內容（螢幕共用）。</span><span class="sxs-lookup"><span data-stu-id="f438f-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

<span data-ttu-id="f438f-106">當團隊偵測到不受支援的瀏覽器時，它會自動顯示一則訊息，說明問題及會話限制。</span><span class="sxs-lookup"><span data-stu-id="f438f-106">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="f438f-107">此訊息提供更多有關存取會議音訊的指示，例如，建議使用者保留回撥號碼，讓小組可以呼叫使用者，或指示使用者撥打會議邀請中包含的會議號碼。</span><span class="sxs-lookup"><span data-stu-id="f438f-107">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="f438f-108">此訊息也會鼓勵使用者下載並使用[小組桌面用戶端](https://teams.microsoft.com/downloads)來取得完整的團隊體驗。</span><span class="sxs-lookup"><span data-stu-id="f438f-108">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="f438f-109">如果 PSTN 無法使用，使用者就不會看到用來存取會議的指示，而且無法加入會議。</span><span class="sxs-lookup"><span data-stu-id="f438f-109">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="f438f-110">瀏覽器限制</span><span class="sxs-lookup"><span data-stu-id="f438f-110">Browser limitations</span></span>

<span data-ttu-id="f438f-111">在不受支援的瀏覽器上使用小組 web app 的人員將會遇到下列限制：</span><span class="sxs-lookup"><span data-stu-id="f438f-111">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="f438f-112">只能透過 PSTN 連接使用音訊。</span><span class="sxs-lookup"><span data-stu-id="f438f-112">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="f438f-113">使用者無法使用其麥克風。</span><span class="sxs-lookup"><span data-stu-id="f438f-113">Users can't use their microphone.</span></span>
- <span data-ttu-id="f438f-114">使用者無法共用其相機，或查看其他參與者的影片，但可以透過影像螢幕共用來查看所呈現的內容。</span><span class="sxs-lookup"><span data-stu-id="f438f-114">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="f438f-115">雖然使用者可以看到其他會議參與者共用的畫面，但他們無法共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="f438f-115">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="f438f-116">使用者在螢幕共用會話期間無法進行控制。</span><span class="sxs-lookup"><span data-stu-id="f438f-116">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="f438f-117">使用者不會收到來電通知。</span><span class="sxs-lookup"><span data-stu-id="f438f-117">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="f438f-118">如果通話中斷，會議就不會自動重新連線。</span><span class="sxs-lookup"><span data-stu-id="f438f-118">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="f438f-119">使用者無法啟動會議。</span><span class="sxs-lookup"><span data-stu-id="f438f-119">Users can't start meetings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f438f-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="f438f-120">Related topics</span></span>

- [<span data-ttu-id="f438f-121">在不受支援的瀏覽器上加入團隊會議</span><span class="sxs-lookup"><span data-stu-id="f438f-121">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
- [<span data-ttu-id="f438f-122">Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="f438f-122">Limits and specifications for Teams</span></span>](/microsoftteams/limits-specifications-teams#browsers)