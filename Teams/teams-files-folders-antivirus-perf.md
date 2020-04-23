---
title: 要從防病毒掃描中排除的 Teams 檔案和資料夾
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 從一般的防病毒掃描中排除特定檔案和資料夾，以改善團隊效能。
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e890509428b3bfba19f6bfb01916e8ea837147
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579589"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>要從防病毒掃描中排除的 Teams 檔案和資料夾
=================================

您可以防止防毒程式掃描特定小組檔案和資料夾，以改善小組部署的整體效能。 這將避免掃描檔案和資料夾上不需要掃描的系統資源開支。

> [!NOTE]
> 當您的使用者彼此下載檔案或共用檔案時，這些檔案不會傳遞到下列區段中所列的位置。 您的使用者上傳、下載或共用檔案的位置，仍會由您的防毒程式定期進行掃描。

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a>要新增至防病毒安全清單的檔案和資料夾

使用您防毒程式支援的程式，將下列檔案和資料夾新增至您的安全清單。 如此一來，就可以避免對這些位置進行防病毒掃描，以節省系統資源。

### <a name="programs"></a>程式

將下列團隊程式新增到您的防病毒安全清單中。

**%localappdata%\Microsoft\Teams\current\Teams.exe**

**%localappdata%\Microsoft\Teams\Update.exe**

