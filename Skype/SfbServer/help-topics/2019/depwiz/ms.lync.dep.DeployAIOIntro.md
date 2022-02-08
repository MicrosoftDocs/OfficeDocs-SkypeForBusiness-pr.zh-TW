---
title: 準備單一 Standard Edition Server (簡介)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: 若要開始安裝會保留中央管理存放區和您所選取之其他組合服務的商務用 Skype Server Standard Edition 伺服器，您必須以將要成為 Standard Edition 伺服器之伺服器上的本機系統管理員群組成員的身分登入。 [準備單一 Standard Edition 伺服器] 頁面詳述初始安裝的需求。 電腦必須是您要部署它所在之網域的成員，而且您必須已成功完成樹系的架構、樹系和網域準備工作。
ms.openlocfilehash: 09904d1c2ae13e88de90174d93d088836cb7101a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385191"
---
# <a name="prepare-single-standard-edition-server-intro"></a>準備單一 Standard Edition Server (簡介)
 
若要開始安裝會保留中央管理存放區和您所選取之其他組合服務的商務用 Skype Server Standard Edition 伺服器，您必須以將要成為 Standard Edition 伺服器之伺服器上的本機系統管理員群組成員的身分登入。 [**準備單一 Standard Edition 伺服器**] 頁面詳述初始安裝的需求。 電腦必須是您要部署它所在之網域的成員，而且您必須已成功完成樹系的架構、樹系和網域準備工作。
  
這項特定工作是用來將 Standard Edition 伺服器設定為您基礎結構中的第一部伺服器。 此工作會將中央管理存放區（SQL Server Express）安裝到 Standard Edition 伺服器上。 如果您已部署另一部 Standard Edition 伺服器或前端集區，則應該按一下 [**取消**]。
  
> [!NOTE]
> 完成此工作之後，如果尚未安裝拓撲產生器 (，請將其安裝) 並設定拓撲檔。 您必須有可用的中央管理存放區（透過完成本主題所述的工作加以部署），才能發行拓撲檔。 
  

