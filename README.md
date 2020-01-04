# react-list Kotlin/JS/React wrapper
This simple repo allows you to use react-list (https://www.npmjs.com/package/react-list) from your Kotlin/JS/React project.

Feel free to turn it into a library, as I'm not sure how (plus, I'm kinda busy).

Example:

    var list: ReactListRef? = null
    
    private fun renderRow(index: Int, key: String): ReactElement? = buildElement {
      // Build your list item here based on the index given and give it the key
    }
    
    override fun RBuilder.render() {
      styledReactList {
        css {
          width = 320.px
        }
        attrs {
          length = yourItems
          itemRenderer = ::renderRow
          type = "variable"
          ref {
            list = it
          }
        }
      }
    }
    
    fun scrollToTop() {
      list?.scrollTo(0)
    }
