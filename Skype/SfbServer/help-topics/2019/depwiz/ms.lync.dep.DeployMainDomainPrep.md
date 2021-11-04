---
title: 準備目前網域
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 若要準備網域以裝載執行商務用 Skype Server 或商務用 Skype Server 使用者的伺服器，您必須完成「步驟5：準備目前的網域」（如使用「安裝程式執行網域準備」主題中所述）。 若要完成此步驟，您必須以您準備的網域中的 domain Admins 群組成員身分登入，或以網域所屬樹系的 Enterprise Admins 群組成員身分登入。 若要準備網域：
ms.openlocfilehash: 782c98d7b2d67a74b11e36493ef2e9f873be0f18
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738689"
---
# <a name="prepare-current-domain"></a>準備目前網域

若要準備網域以裝載執行商務用 Skype Server 或商務用 Skype Server 使用者的伺服器，您必須完成「**步驟5：準備目前的網域**」（如 [使用「安裝程式執行網域準備](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation)」主題中所述）。 若要完成此步驟，您必須以您準備的網域中的 domain Admins 群組成員身分登入，或以網域所屬樹系的 Enterprise Admins 群組成員身分登入。 若要準備網域：

1. 從商務用 Skype Server 安裝資料夾或媒體，執行 Setup.exe 以啟動商務用 Skype Server 部署嚮導。

2. 按一下 **[準備 Active Directory]**，然後等候決定部署狀態。

3. 在 **[步驟 5：準備目前的網域]**，按一下 **[執行]**。

4. 在 **[執行命令]** 頁面上，尋找 **[工作狀態：完成]**，然後按一下 **[檢視記錄檔]**。

5. 在 [ **動作** ] 欄下，依序展開 [ **網域準備**]、[尋找 **\<Success\>** 執行結果]，以驗證網域準備順利完成，請關閉記錄檔，然後按一下 **[完成]**。

> [!TIP]
> [！注意] 如果您需要複查商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行該步驟之 Active directory 網域服務使用者的使用者目錄中，找到執行部署嚮導的電腦。 例如，如果使用者登入網域 Contoso.net 中的網域管理員，則記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp。