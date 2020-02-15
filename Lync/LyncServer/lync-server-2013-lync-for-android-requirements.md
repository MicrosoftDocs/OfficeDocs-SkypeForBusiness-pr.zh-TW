---
title: 'Lync Server 2013: Lync for Android 需求'
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
ms.openlocfilehash: c89439f46c98fd1f00d7cb95eb4a910b26971be0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="9a8d5-102">Lync for Android 需求在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a8d5-102">Lync for Android requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a8d5-103">_**上次修改主題：** 2014年-04-24_</span><span class="sxs-lookup"><span data-stu-id="9a8d5-103">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="9a8d5-104">Microsoft Lync 2013 Microsoft Lync 2013 Android 版提供立即訊息 (IM)、 增強顯示狀態，以及 Lync 會議的貴組織中從 Android 裝置連接的使用者加入功能。</span><span class="sxs-lookup"><span data-stu-id="9a8d5-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="9a8d5-105">本主題說明 Lync 2013 for Android，包括先決條件、 技術需求，以及所需的元件的考量事項。</span><span class="sxs-lookup"><span data-stu-id="9a8d5-105">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="9a8d5-106">Lync for Android 先決條件</span><span class="sxs-lookup"><span data-stu-id="9a8d5-106">Lync for Android Prerequisite</span></span>

<span data-ttu-id="9a8d5-107">若要支援 Lync 2013 for Android，Android 裝置必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="9a8d5-107">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="9a8d5-108">Android 4.0 或更新版本電話或平板電腦導向作業系統，包括平板電腦，除了使用 Tegra2 晶片，必須執行 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="9a8d5-108">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="9a8d5-109">裝置必須有 1.2 GHz 雙核心或更高的 CPU。</span><span class="sxs-lookup"><span data-stu-id="9a8d5-109">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="9a8d5-110">裝置照相機 （前方/後方） 解析度應為 VGA 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="9a8d5-110">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="9a8d5-111">其他硬體需求應該對齊 Android 4.0 相容性定義文件。</span><span class="sxs-lookup"><span data-stu-id="9a8d5-111">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="9a8d5-112">其他技術考量</span><span class="sxs-lookup"><span data-stu-id="9a8d5-112">Other Technical Considerations</span></span>

<span data-ttu-id="9a8d5-113">在 Android 裝置平台上的 Lync 應用程式可以在背景執行。</span><span class="sxs-lookup"><span data-stu-id="9a8d5-113">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="9a8d5-114">因此，不像其他行動裝置平台的推入通知不需要 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="9a8d5-114">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="9a8d5-115">在 Android 裝置上結束 Lync 應用程式的唯一方式是明確登出 Lync。</span><span class="sxs-lookup"><span data-stu-id="9a8d5-115">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="9a8d5-116">Tegra 2 晶片組的裝置不支援此版本的 Lync 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a8d5-116">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

