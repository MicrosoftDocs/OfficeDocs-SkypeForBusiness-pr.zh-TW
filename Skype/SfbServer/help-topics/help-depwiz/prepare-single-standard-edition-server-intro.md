---
title: 準備單一 Standard Edition Server (簡介)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: 若要開始安裝商務用 Skype Server 2015 標準版伺服器，而該伺服器會保留中央管理儲存區及您所選取的其他 collocated 服務，您必須以本機管理員群組的成員身分登入，該伺服器將成為標準版伺服器。 [準備單一 Standard Edition Server] 頁面詳述初始安裝的需求。 該電腦必須是您要部署的所屬網域成員，且您必須為您的樹系成功完成架構、樹系及網域準備工作。
ms.openlocfilehash: a426d734c7644511d31a5b53d3a4939c95f979f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823467"
---
# <a name="prepare-single-standard-edition-server-intro"></a>準備單一 Standard Edition Server (簡介)
 
若要開始安裝商務用 Skype Server 2015 標準版伺服器，而該伺服器會保留中央管理儲存區及您所選取的其他 collocated 服務，您必須以本機管理員群組的成員身分登入，該伺服器將成為標準版伺服器。 [準備單一 Standard Edition Server]**** 頁面詳述初始安裝的需求。 該電腦必須是您要部署的所屬網域成員，且您必須為您的樹系成功完成架構、樹系及網域準備工作。
  
此項特殊工作是專門用來安裝 Standard Edition 伺服器以作為基礎結構中第一部伺服器。 此工作會將中央管理儲存區（即 SQL Server Express）安裝到標準版伺服器。 如果您已經部署了另一部 Standard Edition 伺服器或前端集區，則請按一下 [取消]****。
  
> [!NOTE]
> 完成這項工作之後，您將會安裝拓撲建立器（如果尚未安裝），並設定您的拓撲檔。 您必須要有可用的中央管理存放區 (完成此主題中說明的工作來部署)，才能發行拓樸文件。 
  

