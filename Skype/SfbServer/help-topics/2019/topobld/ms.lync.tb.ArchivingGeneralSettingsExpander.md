---
title: 封存伺服器一般設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 在 [拓撲產生器] 中，您可以編輯執行封存之個別伺服器的屬性，方法是在主控台樹中以滑鼠右鍵按一下執行封存的伺服器，然後按一下工具列中的 [動作]，或是按一下 [動作] 窗格中的工作，然後按一下 [編輯內容] 並變更下列任一選項：
ms.openlocfilehash: a16c239706bfc83a2798f26b05386429dfa80c6b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584197"
---
# <a name="archiving-server-general-settings-expander"></a>封存伺服器一般設定展開工具
 
在 [拓撲產生器] 中，您可以編輯執行封存之個別伺服器的屬性，方法是在主控台樹中以滑鼠右鍵按一下執行封存的伺服器，然後按一下工具列中的 [ **動作** ]，或是按一下 [動作] 窗格中的工作，然後按一下 [ **編輯** 內容] 並變更下列任一選項：
  
- **FQDN**，以變更您要部署為執行封存之伺服器的原有伺服器完整網域名稱 (FQDN)。
    
- **SQL 存放區**，以變更要用作封存 SQL Server 資料庫的 SQL Server 執行個體。如果您變更執行封存之伺服器的 SQL Server 資料庫，必須重新啟動執行封存的伺服器以確保變更生效。
    
- **檔案共用**，以變更要用作封存檔案存放區的資料夾。如果您變更執行封存之伺服器的檔案共用，必須重新啟動執行封存的伺服器以確保變更生效。此外，您必須將先前的會議檔案移至新的檔案存放區資料夾以避免遺失封存的會議檔案。
    
> [!NOTE]
> 若要變更與執行封存之伺服器關聯的集區，請針對目前與執行封存之伺服器關聯的個別前端集區節點或 Survivable Branch Appliance 節點，選取 [編輯內容] 選項。
  
> [!NOTE]
> 如果您先前已在拓撲產生器中將執行封存的伺服器新增至拓撲，則 [封存] 節點會包含執行封存的伺服器。 您可以編輯清單中的任何一部執行封存的伺服器內容。 不過，直到您也為執行封存的伺服器設定服務後，才能封存立即訊息或 web 會議 (郵件) 。 
  

