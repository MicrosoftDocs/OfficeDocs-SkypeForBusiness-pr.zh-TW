---
title: 準備目前的網域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 若要準備網域以主持執行商務用 Skype Server 或商務用 Skype Server 使用者的伺服器，您必須完成步驟5：準備目前的網域，如使用安裝程式執行網域準備主題中所述。 若要完成此步驟，您必須以目前準備之網域中的 Domain Admins 群組成員身分，或網域所屬之樹系的 Enterprise Admins 群組成員身分登入。 若要準備網域，請執行下列操作：
ms.openlocfilehash: 966f80fe799529ec4d208318fa417146db67ea13
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705438"
---
# <a name="prepare-current-domain"></a>準備目前的網域

若要準備網域以主持執行商務用 Skype Server 或商務用 Skype Server 使用者的伺服器，您必須完成**步驟5：準備目前的網域**，如[使用安裝程式執行網域準備](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)主題中所述。 若要完成此步驟，您必須以目前準備之網域中的 Domain Admins 群組成員身分，或網域所屬之樹系的 Enterprise Admins 群組成員身分登入。 若要準備網域，請執行下列操作：

1. 從商務用 Skype Server 安裝資料夾或媒體，執行 setup.exe 以啟動商務用 Skype Server 部署嚮導。

2. 按一下 [準備 Active Directory]****，然後等候決定部署狀態。

3. 在 [步驟 5：準備目前的網域]****，按一下 [執行]****。

4. 在 [執行命令]**** 頁面上，尋找 [工作狀態：完成]****，然後按一下 [檢視記錄檔]****。

5. 在 [**動作**] 欄底下，展開 [**網域準備**]，尋找每個工作** \< \> **結尾的成功執行結果，確認已成功完成 [網域準備]，然後關閉記錄，然後按一下 **[完成]**。

> [!TIP]
> 如果您需要查看由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行步驟之 Active Directory 網域服務使用者的使用者目錄中，找到運行 [部署嚮導] 的電腦上的日誌檔。 例如，如果使用者是以網域 Contoso.net 的網域管理員身分登入，則記錄檔案位於： C:\Users\Administrator.Contoso\AppData\Local\Temp。


