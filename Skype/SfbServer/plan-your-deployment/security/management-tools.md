---
title: Windows PowerShell 和商務用 Skype Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: '在商務用 Skype Server 中, 管理工具是使用 Windows PowerShell 來實現。 Windows PowerShell 包含命令列環境、產品特定命令及完整的腳本撰寫語言。 使用 Windows PowerShell 執行的商務用 Skype Server 工具組括下列各項:'
ms.openlocfilehash: 3eb156e002603378ec77fbbcbde4772870aad907
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192941"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell 和商務用 Skype Server 管理工具
 
在商務用 Skype Server 中, 管理工具是使用 Windows PowerShell 來實現。 Windows PowerShell 包含命令列環境、產品特定命令及完整的腳本撰寫語言。 使用 Windows PowerShell 執行的商務用 Skype Server 工具組括下列各項: 
  
- **拓撲**建立器。 您可以使用 [拓撲建立器] 來建立、調整及發佈規劃的拓撲, 並在開始伺服器安裝之前驗證您的拓撲。 當您在個別伺服器上安裝商務用 Skype Server 時, 伺服器會讀取已發佈的拓撲 (作為安裝程式的一部分), 而安裝程式會以拓撲中的指示方式來部署伺服器。 安裝完成後, 系統會自動將配置資訊複製到所有伺服器。 只有使用拓撲建立器, 才能將元件新增至您的部署。
    
- **商務用 Skype Server 管理命令**介面。 您可以使用商務用 Skype 伺服器管理命令介面, 以進行部署的完整命令列管理。
    
- **商務用 Skype Server**的 [控制台]。 您可以使用商務用 Skype Server 的 [控制台] 使用者介面來管理部署中最常見的工作。
    
這些工具使用 Windows PowerShell Cmdlet 來管理您的部署, 包括關閉至550產品專用的 Cmdlet。 商務用 Skype 伺服器中包含的安全性 Cmdlet 主要是用來管理驗證, 以及使用者權利和許可權。 有多種不同的 Cmdlet 可用於管理驗證, 包括憑證和個人識別碼 (PIN) 驗證的 Cmdlet。 此外, 有許多 Cmdlet 可讓您使用新的角色存取控制 (RBAC) 功能來委派商務用 Skype Server 的管理控制權。 如需商務用 Skype Server Cmdlet 的詳細資訊, 請參閱[商務用 Skype Server 管理命令](../../manage/management-shell.md)介面。
  
Windows PowerShell 的腳本安全性功能是專門設計來協助避免舊版技術的一些腳本相關安全性問題, 包括 Microsoft Visual Basic 腳本版本 (VBScript)。 Windows PowerShell 安全性功能是用來建立使用者無法輕易或無意中執行腳本的環境。 根據預設, 會啟用 Windows PowerShell 安全性功能。 您可以修改這些功能的狀態, 以適應您的腳本需求, 以及各種安全目標。 這不是說 shell 無法讓使用者執行腳本。 相反地, shell 會讓使用者在執行腳本時不會有任何困難 (預設), 而不會意識到這麼做。 如需詳細資訊, 請參閱[Windows PowerShell 腳本安全性](https://go.microsoft.com/fwlink/p/?LinkId=213145)。
  

