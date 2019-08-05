---
title: 準備架構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: 若要準備 Active Directory 網域服務的架構, 請在商務用 Skype Server 部署嚮導中執行 [準備架構] 步驟。 按一下 [執行]，開始準備架構。 [準備架構] 步驟會在執行 [部署嚮導] 的系統上, 閱讀/Program Files/Microsoft Lync Server 2013/部署/設定目錄中提供的架構定義檔案。 您也可以在支援/架構目錄中的安裝媒體上取得這些檔案。 [準備架構] 步驟會擴充架構並報告程序的狀態。 程序完成時也會通知您。 摘要畫面可讓您檢視程序的記錄。 請檢閱記錄來確定已順利完成準備。
ms.openlocfilehash: 12b4bcbe93bd1ed55e0a2c2c1a133db41b30cd00
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192308"
---
# <a name="prepare-schema"></a>準備架構
 
若要準備 Active Directory 網域服務的架構, 請在商務用 Skype Server 部署嚮導中執行 [準備架構] 步驟。 按一下 [執行]****，開始準備架構。 [準備架構] 步驟會讀取在執行 [部署精靈] 的系統上的 \Program Files\Microsoft Lync Server 2013\Deployment\Setup 目錄中提供的架構定義檔案。 安裝媒體的 \Support\Schema 目錄中也提供這些檔案。 [準備架構] 步驟會擴充架構並報告程序的狀態。 程序完成時也會通知您。 摘要畫面可讓您檢視程序的記錄。 請檢閱記錄來確定已順利完成準備。
  
> [!IMPORTANT]
> 若要擴充架構，您必須以 Schema Admins 群組和 Enterprise Admins 群組的成員身分登入網域。 
  
新增類別和屬性是為了支援商務用 Skype Server 2015 server、service 和 user 物件, 將 Active Directory 網域服務架構擴充。 在擴充架構之前，您應該建立扮演架構主機角色的網域控制站的系統狀態備份。 如需有關 Windows Server 2008 R2 (含 SP1) 備份程式的詳細[https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198)資訊, 請參閱。 若為 Windows Server 2003 和 Windows Server 2003 R2, [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199)請參閱。
  
> [!CAUTION]
> 擴充架構之後無法還原。 您應該致力限制架構延伸模組失敗可能的影響範圍，並確保架構擴充成功。 在伺服器發生失去通訊或任何其他失敗時，這一點尤其重要。 您應該執行架構主機網網域控制站的備份以及 Active Directory 的完整備份。 
  
若要執行架構主機網網域控制站的備份, 以及 Active Directory 的完整備份:
  
1. 將扮演架構主機角色的網域控制站與網路切斷連線。
    
2. 對扮演架構主機的網域控制站執行系統狀態備份。
    
3. 擴充架構。
    
4. 成功擴充架構時，將網域控制站重新連線至網路，並確定複寫在作用中且正常運作。
    
5. 在架構延伸失敗事件發生時, 請使用您先前所做的系統狀態備份來還原網網域控制站和 Active Directory 的系統狀態。
    
> [!NOTE]
> 如果您需要查看由商務用 Skype Server 部署嚮導所建立的記錄檔, 您可以在執行步驟的 Active Directory 使用者的使用者目錄中, 找到執行部署嚮導之電腦上的檔案。 例如, 如果使用者是以網域 Contoso.net 的網域管理員身分登入, 則記錄檔案位於: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

