<template>
  <footer class="footer">
    <div class="container font-italic text-muted text-center">
      <div class="mg-additional-footer-message" v-if="additionalMessage" v-html="additionalMessage">
      </div>
      <div>
        This database was created using the open source <a :href="molgenisSite">MOLGENIS software </a>
        <span v-if="version">
          {{version}}
        </span>
        <span v-if="buildDate">
          built on {{buildDate}}.
        </span>
      </div>
      <div v-if="appVersion">
        App version: {{appVersion}}.
      </div>
      <p>
        Please cite <a href="https://www.ncbi.nlm.nih.gov/pubmed/30165396">Van der Velde et al (2018)</a>, <a href="https://www.ncbi.nlm.nih.gov/pubmed/21210979">Swertz et al (2010)</a> or <a href="https://www.ncbi.nlm.nih.gov/pubmed/17297480">Swertz &amp; Jansen(2007)</a> on use.
      </p>
    </div>
  </footer>
</template>

<script>

import { MolgenisFooter } from '../types'
export default {
  name: 'FooterComponent',
  props: {
    molgenisFooter: MolgenisFooter
  },
  data: function () {
    return {
      additionalMessage: this.molgenisFooter.additionalMessage,
      version: this.molgenisFooter.version,
      buildDate: this.molgenisFooter.buildDate,
      appVersion: this.molgenisFooter.appVersion,
      molgenisSite: this.molgenisFooter.molgenisSite
    }
  }
}
</script>
