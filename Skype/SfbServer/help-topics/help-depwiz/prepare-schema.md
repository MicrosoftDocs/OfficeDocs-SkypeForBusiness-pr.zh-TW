---
title: 準備架構
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: 若要為 Active Directory 網域服務準備架構，您可以在商務用 Skype Server 部署嚮導中執行 [準備架構] 步驟。 按一下 [執行]，開始準備架構。 [準備架構] 步驟會在執行部署嚮導的系統上，于/Program Files/Microsoft Lync Server 2013/部署/安裝目錄中讀取所提供的架構定義檔案。 您也可以在支援/架構目錄的安裝媒體上使用這些檔案。 [準備架構] 步驟會擴充架構並報告程序的狀態。 程序完成時也會通知您。 摘要畫面可讓您檢視程序的記錄。 請檢閱記錄來確定已順利完成準備。
ms.openlocfilehash: c4e1faa8a26fa74579d9c9177d2efbfda29fa40f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849046"
---
# <a name="prepare-schema"></a>準備架構
 
若要為 Active Directory 網域服務準備架構，您可以在商務用 Skype Server 部署嚮導中執行 [準備架構] 步驟。 按一下 **[執行]**，開始準備架構。 [準備架構] 步驟會在執行部署嚮導之系統上的 \Program Files\Microsoft Lync Server 2013\Deployment\Setup 目錄中讀取所提供的架構定義檔案。 安裝媒體的 \Support\Schema 目錄中也提供這些檔案。 [準備架構] 步驟會擴充架構並報告程序的狀態。 程序完成時也會通知您。 摘要畫面可讓您檢視程序的記錄。 請檢閱記錄來確定已順利完成準備。
  
> [!IMPORTANT]
> 若要擴充架構，您必須以 Schema Admins 群組和 Enterprise Admins 群組的成員身分登入網域。 
  
新增類別和屬性以擴充 Active Directory 網域服務架構，以支援商務用 Skype Server 2015 Server、service 及 user 物件。 在擴充架構之前，您應該建立扮演架構主機角色的網域控制站的系統狀態備份。 如需 Windows Server 2008 R2 （含 SP1）備份程式的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=207198](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee849849(v=ws.10)) 。 如 Windows server 2003 和 Windows Server 2003 R2，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=207199](/previous-versions/windows/it-pro/windows-server-2003/cc787254(v=ws.10)) 。
  
> [!CAUTION]
> 擴充架構之後無法還原。 您應該致力限制架構延伸模組失敗可能的影響範圍，並確保架構擴充成功。 在伺服器發生失去通訊或任何其他失敗時，這一點尤其重要。 您應該對架構主機網域控制站執行備份，並執行 Active Directory 的完整備份。 
  
若要執行架構主機網域控制站的備份和 Active Directory 的完整備份：
  
1. 將扮演架構主機角色的網域控制站與網路切斷連線。
    
2. 對扮演架構主機的網域控制站執行系統狀態備份。
    
3. 擴充架構。
    
4. 成功擴充架構時，將網域控制站重新連線至網路，並確定複寫在作用中且正常運作。
    
5. 在架構擴充失敗的情況下，請使用您先前建立的系統狀態備份，還原網域控制站和 Active Directory 的系統狀態。
    
> [!NOTE]
> [！注意] 如果您需要複查商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行該步驟的 Active directory 使用者的使用者目錄中，找到執行「部署」嚮導」之電腦上的檔案。 例如，如果使用者登入網域 Contoso.net 中的網域管理員，則記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp 
