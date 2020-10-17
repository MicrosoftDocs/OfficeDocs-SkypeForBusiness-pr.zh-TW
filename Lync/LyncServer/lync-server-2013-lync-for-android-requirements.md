---
title: Lync Server 2013： Lync for Android 需求
description: Lync Server 2013： Lync for Android 的需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync for Android requirements
ms:assetid: 4ff53e03-0c1f-4a2b-9cec-1131c2a48563
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690980(v=OCS.15)
ms:contentKeyID: 53312965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d3d3aa6e428c3a73f1b9263fe9cf13e5aa9fff0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570469"
---
# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="ab847-103">Lync Server 2013 中的 lync for Android 需求</span><span class="sxs-lookup"><span data-stu-id="ab847-103">Lync for Android requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab847-104">_**主題上次修改日期：** 2014-04-24_</span><span class="sxs-lookup"><span data-stu-id="ab847-104">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="ab847-105">Microsoft Lync 2013 Microsoft Lync 2013 for Android 為組織中從 Android 裝置連線的使用者，提供立即訊息 (IM) 、增強型目前狀態，以及 Lync 會議加入功能。</span><span class="sxs-lookup"><span data-stu-id="ab847-105">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="ab847-106">本主題說明適用于 Android 的 Lync 2013 考慮，包括先決條件、技術需求及必要元件。</span><span class="sxs-lookup"><span data-stu-id="ab847-106">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="ab847-107">Lync for Android 先決條件</span><span class="sxs-lookup"><span data-stu-id="ab847-107">Lync for Android Prerequisite</span></span>

<span data-ttu-id="ab847-108">若要支援適用于 Android 的 Lync 2013，Android 裝置必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="ab847-108">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="ab847-109">Android 裝置必須執行 Android 4.0 或更新版本的裝置作業系統（包括平板電腦），但不含 Tegra2 晶片。</span><span class="sxs-lookup"><span data-stu-id="ab847-109">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="ab847-110">裝置必須具有 1.2 GHz 雙核心或更高的 CPU。</span><span class="sxs-lookup"><span data-stu-id="ab847-110">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="ab847-111">裝置攝像頭 (前置/後) 解析度應為 VGA 或更高。</span><span class="sxs-lookup"><span data-stu-id="ab847-111">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="ab847-112">其他硬體需求應與 Android 4.0 相容性定義檔對齊。</span><span class="sxs-lookup"><span data-stu-id="ab847-112">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="ab847-113">其他技術考量</span><span class="sxs-lookup"><span data-stu-id="ab847-113">Other Technical Considerations</span></span>

<span data-ttu-id="ab847-114">在 Android 裝置平臺上，Lync 應用程式可以在後臺執行。</span><span class="sxs-lookup"><span data-stu-id="ab847-114">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="ab847-115">因此，與其他行動裝置平臺不同的是，Android 裝置不需要推播通知。</span><span class="sxs-lookup"><span data-stu-id="ab847-115">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="ab847-116">在 Android 裝置上退出 Lync 應用程式的唯一方法，就是以明確方式登出 Lync。</span><span class="sxs-lookup"><span data-stu-id="ab847-116">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="ab847-117">Tegra 2 晶片組的裝置不支援此版本的 Lync 應用程式。</span><span class="sxs-lookup"><span data-stu-id="ab847-117">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

