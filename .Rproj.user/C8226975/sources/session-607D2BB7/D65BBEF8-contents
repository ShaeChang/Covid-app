# setup -----------------------------------------

library(shiny)
library(shinydashboard)
library(sf)
library(tidyverse)

# load data that don't need to change over time

us_states <-
  st_read('data/us_states.geojson') %>% 
  select(name_en, postal)

# ui --------------------------------------------

ui <-
  dashboardPage(
    dashboardHeader(title = 'Covid app'),
    
    # sidebar
    
    dashboardSidebar(
      sidebarMenu(
        menuItem(text = 'Overview',
                 icon = icon('book'),
                 tabName = 'overview'),
        
        menuItem(text = 'Map',
                 icon = icon('map'),
                 tabName = 'maps'),
        
        menuItem(text = 'Table',
                 icon = icon('table'),
                 tabName = 'tables'),
        
        menuItem(text = 'Trend',
                 icon = icon('chart-line'),
                 tabName = 'charts'))
    ),
    
    # dashboard body
    
    dashboardBody(
      
      # 'tags' is a list object where each list item is a tag function,
      # a more complete set of tag functions is available with this object.
      
      tags$head(
        tags$link(
          rel = 'stylesheet',
          type = 'text/css',
          href = 'dashboard_styles.css'
        )
      ),
      tabItems(
        tabItem(tabName = 'overview',
                h2('Overview'),
                p('Here is an example shiny application that uses a dashboard
                  interface. We will use this app to explore data on the 
                  temporal and spatial distribution of Covid-19.'),
                p('Click the menu items in the sidebar menu on the left to 
                  explore what this app can do!')),
        tabItem(tabName = 'maps',
                h2('Maps')),
        tabItem(tabName = 'tables',
                h2('Tables')),
        tabItem(tabName = 'charts',
                h2('Trend'))
      )
    )
  )

# server ----------------------------------------

server <-
  function(input, output) { 
  }

# knit and run app ------------------------------

shinyApp(ui, server)

